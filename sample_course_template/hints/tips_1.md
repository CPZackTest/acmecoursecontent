## Project 1 (Instagram Client) Helpful Hints

Here's a list of useful notes you may find helps save you time while developing the Instagram Client or running into problems:

* **Problem #0: Encountering issues with Android Async Http or `package org.apache.http` does not exist?**  The Apache HTTP library is no longer included in Android Marshmallow (API version 23) which causes issues with android-async-http.  See this [setup section](https://guides.codepath.com/android/Using-Android-Async-Http-Client#setup) for a workaround.

* **Tip #1**: Make sure to review the [Instagram API](http://instagram.com/developer/endpoints/media/) and what the expected response looks like.

* **Tip #2**: Scrolling vertically on Android emulator is done via pushing down on the left mouse and dragging up as you would do to scroll with your finger on the device.

* **Problem #1**: Can't get back the JSON Response! A number of people always run into issues with their emulator and not being able to access the Instagram API. If you are pretty sure you have the code right and you can't seem to get any response back from the API, try these steps:
 * Getting `No address associated with hostname` exception? Emulator doesn't have internet, try a restart.
 * Check the URL to ensure that you are passing the correct `client_id` with the request.
 * Make sure you have added the internet permission
 `<uses-permission android:name="android.permission.INTERNET" />` to your manifest.
 * Ensure the emulator has [access to the internet](http://i.imgur.com/kZqZko6.gif), otherwise all network requests fail.
 * Restart the emulator (close window and relaunch) until you have verified internet access above.
 * Obtain the exact url (by breakpointing or logging) that you are going to send a request to and paste the url into your browser to verify the API response is coming back correctly.
 * Make sure you are using the `new JsonHttpResponseHandler()`([docs](http://loopj.com/android-async-http/doc/com/loopj/android/http/JsonHttpResponseHandler.html)) in your AsyncHttpClient  network call and make sure you are sending
 `client.get(url, new JsonHttpResponseHandler() { ... })`
 * Verify that the onSuccess signature is correct. The Image search API returns a JSON dictionary so make sure the onSuccess is using JSONObject and not JSONArray in this case. This is entirely dependent on whether a dictionary or array is the root object i.e
 `public void onSuccess(int statusCode, Header[] headers, JSONObject response)`
 * Add an `onFailure` to the `JsonHttpResponseHandler` callbacks and log there to ensure that its not being hit
 * Check your LogCat to make sure there are no specific error messages (and watch this [debugging video](http://courses.codepath.com/course_videos/intro_to_android/73990805) for more tips), use filters to more easily read the log.
 * [Uninstall the app](http://stackoverflow.com/questions/12447839/how-to-uninstall-my-app-from-android-emulator-on-a-mac-10-7-4) from the emulator and allow it to be fully re-installed by relaunching it from within Android Studio.

* **Problem #2**: Parsing JSON data can raise an exception if certain keys are null! When parsing JSON data, you want to program defensively and verify that keys exist and are not null. You can verify that a key exists with the `notNull` method or optionally extract a key (only if it exists) with the `opt` prefix method. For example, `if (photoJSON.optJSONObject("caption") != null) { ... }` will extract the caption only if the caption is not null and will return null otherwise.

* **Tip #3**: To make the UI of your Instagram client look more like the actual Instagram app, switch to XML view of your activity layout and play around with different [attributes](http://guides.codepath.com/android/Defining-Views-and-their-Attributes). Read more about this in our [RelativeLayout Cliffnotes](http://guides.codepath.com/android/Constructing-View-Layouts#relativelayout).

* **Tip #4**: In order to have a single row of text which has two different styles (i.e username styled differently from comment), we can use a single `TextView` leveraging the spannable functionality to [format our TextView body using basic HTML](http://guides.codepath.com/android/Working-with-the-TextView#inserting-html-formatting).

* **Tip #5**: Making the photo appear more like the display on the official Instagram provides time for experimentation with a few different properties.
  * First, check out the different [scale types](http://guides.codepath.com/android/Working-with-the-ImageView#scale-types) for the ImageView and make sure to set `adjustViewBounds` to true.
  * When loading with Picasso, experiment with different loading behaviors such as `.fit().centerInside()` or `.resize(x, y)` specified before the `.into(...)` command.
  * To resize an image and preserve aspect ratio, as of Picasso 2.4.0 you can simply supply `0` for one of the arguments i.e `.resize(150, 0)`
  * If you want to determine the width of the screen, you can check the width of the layout item or use this [device dimensions helper](https://gist.github.com/nesquena/318b6930aac3a56f96a4)
  * In the adapter, you can calculate the aspect ratio of the image (`width / height`) and then set the ImageView width to screen width and the height to correct calculated height to maintain the aspect ratio of the image.

* **Tip #6**: To display the photo date as a relative timestamp, we can use `DateUtils`. The Instagram API returns unix timestamps in the long format of `1382576494`. To convert these into relative dates, we just need to multiply the long date by 1000: `DateUtils.getRelativeTimeSpanString(longCreatedAt * 1000, ..., ...)` and this will return a relative string such as "4 hours ago". See [this article](http://chris.banes.me/2013/01/15/snippet-dateutils/) for how to display relative timestamps.

* **Tip #7**: For displaying rounded images such as for a profile image using Picasso, you can apply a [rounded transform](http://stackoverflow.com/a/26112408/313399) as outlined. You can load the image using picasso and apply the transform to create the rounding effect. Alternatively, check out the third-party [RoundedImageView](https://github.com/vinc3m1/RoundedImageView) library which makes rounded images easy to display.  There's also an official solution in the support library called [RoundedBitmapDrawable](http://stackoverflow.com/a/24879522/313399).

* **Tip #8**: To improve the performance of any `ListView`, be sure to implement the [ViewHolder pattern](http://guides.codepath.com/android/Using-an-ArrayAdapter-with-ListView#improving-performance-with-the-viewholder-pattern) on any adapters you create. Every custom adapter should use that pattern to speed up scrolling and item loading. In short, this pattern prevents the unnecessary lookup of the views being populated for each row every time you scroll.

* **Tip #9**: To use a custom launcher icon for the app, you can first download any image from [IconFinder](https://www.iconfinder.com/). Within the Android project select `New → Image Asset` and browse to find the image file.  You can use this tool which will generate the launcher icon specified for all drawable density folders.

* **Tip #10**: When displaying comments in each item, avoid ever embedding a ListView within another ListView item. This rarely goes well and is considered an anti-pattern. Instead, simply inflate the and append the comments into a layout container as [outlined here](http://stackoverflow.com/questions/3135112/android-nested-listview/5983743#5983743). The idea here is to create an empty comment container within each photo row which can be filled with inflated comments within `getView` in the adapter.
