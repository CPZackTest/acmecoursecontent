## Project 2 (Image Search) Helpful Hints

Here's a list of useful notes you may find helps save you time while developing the Image Search or running into problems:

* **Problem #0: When trying to check the response from Google, most of the response data appears to be garbled.**  There is a bug in older versions for Android Async Http Client that causes Gzip decoding errors.  Upgrade to the [latest version](https://guides.codepath.com/android/Using-Android-Async-Http-Client#setup).

* **Tip #1:** This entire app revolves around the [Google Image Search API](https://developers.google.com/image-search/v1/jsondevguide#json_reference). Make sure to review the API, and what parameters it takes. Also, what the response looks like. Keep in mind there are parameters for each search filter (i.e `imgsz`), result size (`rsz`, max 8) and result offset (`start`) which will all be used.

* **Tip #2:** Applications that are using `ActionBarActivity` and the support actionbar need to call `getSupportActionBar()` instead of `getActionBar()` to obtain access at runtime.

* **Tip #3:** Scrolling vertically on Android emulator is done via pushing down on the left mouse and dragging up as you would do to scroll with your finger on the device.

* **Problem #1: Can't get back the JSON Response!** A number of people always run into issues with their emulator and not being able to access the google image search API. If you are pretty sure you have the code right and you **can't seem to get any response back** from the API, try these steps:
  * Make sure you are using version 1.4.9 or later of the [android-async-http](https://guides.codepath.com/android/Using-Android-Async-Http-Client#setup) library.
  * Check the URL to ensure that you have properly formed the query string (i.e `rsz` should be **set to 8**)
  * Make sure you have added the internet permission `<uses-permission android:name="android.permission.INTERNET" />` to your manifest.
  * If you are getting "Unable to resolve host", Check your WiFi connection and then go to the browser on the phone and verify you can access google. If you cannot, try checking the wifi setting and turning it off and on until the internet works (you may need to restart the emulator)
  * Ensure the emulator has [access to the internet](http://i.imgur.com/kZqZko6.gif), otherwise all network requests fail.
  * Restart the emulator (close window and relaunch) until you have verified internet access above.
  * Obtain the exact url (by breakpointing or logging) that you are going to send a request to and paste the url into your browser to **verify the API response** is coming back correctly.
  * Make sure you are using the `new JsonHttpResponseHandler()` ([docs](http://loopj.com/android-async-http/doc/com/loopj/android/http/JsonHttpResponseHandler.html)) in your AsyncHttpClient network call and make sure you are sending `client.get(url, new JsonHttpResponseHandler() { ... })`
  * Verify that the `onSuccess` signature is correct. The Image search API returns a JSON dictionary so make sure the onSuccess is using `JSONObject` and not `JSONArray` in this case. This is entirely dependent on whether a dictionary or array is the root object i.e `public void onSuccess(JSONObject response)`
  * Add an `onFailure` to the `JsonHttpResponseHandler` callbacks and log there to ensure that its not being hit
  * Check your LogCat to make sure there are no specific error messages (and watch this [debugging video](https://player.vimeo.com/video/73990805) for more tips), use filters to more easily read the log.
  * [Uninstall the app](http://stackoverflow.com/questions/12447839/how-to-uninstall-my-app-from-android-emulator-on-a-mac-10-7-4) from the emulator and allow it to be fully re-installed by relaunching it from within Android Studio.
  
* **Tip #4:** Google Image Search API maxes out at about **8 pages of results** for a search for a **maximum of 64 results**. If you try to go more than 8 pages, expect the additional requests for image results to fail. This is simply a limitation of the Google Image Search API being used so do not consider this a bug.

* **Problem #2: Can't get infinite scroll working!** This assignment wants us to create an "infinite scroll" feature for our Grid of images so users can scroll through pages of images easily. Check out the [endless pagination cliffnotes](http://guides.codepath.com/android/Endless-Scrolling-with-AdapterViews-and-RecyclerView) for more information on how to get this working.
  * Google Image Search API maxes out at about **8 pages of results** for a search for a **maximum of 64 results**. This is a limitation of the API and not a fixable bug.
  * Make sure that as you load more items that you are **appending** new results to the adapter and **not clearing the existing items each time you paginate**. Only clear the results in the adapter when a fresh search is being initiated.
  * If you are having trouble with having more than 8 items loading at a time, ensure that you are **not incorrectly clearing the adapter** of items during each subsequent pagination. When a new search is initiated (with fresh search term), we should **clear the adapter of results** but on subsequent requests for more results **do not clear the adapter of results**, instead you should append to it. Make sure to clear the **adapter rather than the array** on a fresh search for reliable pagination behavior.
  * Keep in mind that the `onLoadMore` method for the endless pagination doesn't fire very often since it's "smart" and doesn't get called just when you scroll. It tries to be conservative and only calls `onLoadMore` when new items actually need to be loaded from the server (which means that you have scrolled far enough down and new items have been added already since the last call and now we need to load even more items. So until you start appending items into the gridview, you aren't expected to see multiple calls to scroll.
  * If pagination works for you on the first search but you are having issues with pagination on any subsequent searches, make sure to clear the **adapter rather than the array** for when a new search is being initiated.
  * **Offset not Page** - Paginating for infinite scroll requires us to look at the [API docs](https://developers.google.com/image-search/v1/jsondevguide#request_format) for the parameter `start` that allows us to pass an "offset" for the results which is what lets us paginate. Make sure your call to load more results properly includes the offset in the url request.
  * **Seeing Duplicate Images?** - If you are seeing the same images over and over as you scroll, be sure to verify you are passing the **offset and not the page** to the `start` parameter in the API. In other words to paginate, you want to send `start=8` and then `16 => 24 => 32` as you scroll to retrieve new images each time.
  * **Tweaking the Listener** - If you are still unable to see new images being loaded in certain cases, you may want to reduce the value of the `visibleThreshold` variable in the `EndlessScrollListener` to see if that helps trigger more frequent paginations.

* **Tip #5:** This assignment has an optional user story which involves being able to share an image out to other services. Sharing is done through the use of intents as [explained in the cliffnotes](http://guides.codepath.com/android/Sharing-Content-with-Intents).

* **Problem #3: Large images on the detail view don't load with an memory exception!** This is because very large bitmaps have to [be resized down](http://guides.codepath.com/android/Working-with-the-ImageView#scaling-a-bitmap) before being inserted into an ImageView. Fortunately, the [picasso library](http://square.github.io/picasso/) has the ability to resize images built in  using `Picasso.load(...).into(...).fit()` command which resizes an image and maintains the aspect ratio.

* **Note #1:** This assignment requires us to add an clickable icon to the ActionBar, see [ActionBar Cliffnotes](http://guides.codepath.com/android/Defining-The-ActionBar) for more details on this.
  * To create icons that work for your ActionBar, you can use the **File => New => Image Asset, select Action Bar and Tab Icon for Asset Type.**  Check out the [step-by-step guide](http://imgur.com/BI5gWPF.png).

* **Note #2:** This assignment requires us to **launch a new activity using an intent** and then somehow communicate the filters to apply back to the search activity. See the [intents cliffnotes](http://guides.codepath.com/android/Using-Intents-to-Create-Flows#returning-data-result-to-parent-activity) for a review of that and passing data to and from activities.

* **Note #3:** This assignment suggests for us to use dropdown spinners to display options to the user. Check out the [input views cliffnotes](http://guides.codepath.com/android/Working-with-Input-Views#spinners) for more about how to use spinner.
  * Customizing the look of spinner items requires you creating a spinner adapter and supplying your own custom spinner item XML file similar to a [custom list adapter](http://stackoverflow.com/a/9476736).

* **Tip #6:** To simulate the loss of internet on your emulator, in Android Studio go to `Tools` -> `Android` -> `Android Device Monitor` -> and then select the "Emulator Control" tab. Use the "Data" area to simulate losing access to the internet when testing network connection failures in your app.

* **Tip #7:** If you want to implement the search box within the action bar, check out the [SearchView guide](http://guides.codepath.com/android/Extended-ActionBar-Guide#adding-searchview-to-actionbar) for a simple method that doesn't require a separate search activity or provider. We can even implement search suggestions as you type using the method [outlined in this post](http://stackoverflow.com/a/13773625) although this requires quite a bit of setup.

* **Problem #4: ActionBar Back Button resets parent activity** In this project we introduce the use of `android:parentActivityName` to [declare the logical parent activity](http://developer.android.com/training/implementing-navigation/temporal.html#SynthesizeBackStack) of the detail activity. This enables a "back button" in the ActionBar but by default creates a new instance of the parent activity in the task stack. See [this stackoverflow post](http://stackoverflow.com/questions/12276027/how-can-i-return-to-a-parent-activity-correctly) to fix this by [adjusting the launch mode](http://guides.codepath.com/android/Navigation-and-Task-Stacks#launch-modes) of the activity.

* **Problem #5: Methods such as `onQueryTextSubmit` are being called twice** Designing robust Android software means properly handling cases where events are triggered twice or more in quick succession. Ensure that your code is [idempotent where possible](https://en.wikipedia.org/wiki/Idempotence#Computer_science_meaning) where an event being triggered multiple times has no side effects.
