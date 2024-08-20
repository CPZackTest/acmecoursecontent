## Week 2 Project: Grid Image Search

**Due:** {{PROJECT(2) | longdate}} at 10pm

**Overview**: Build a Google Image Search app which allows a user to select search filters and paginate results infinitely.

**Guide**: Please review the @[[Weekly Projects Slide Deck|slides/Weekly Projects Overview.pdf]] for a more detailed visual guide for building this app.

**Walkthrough:** Check out the provided [video walkthrough](https://player.vimeo.com/video/70808495) for this project to get you started. Check the [Project 2 Tips Guide](#!hints) to troubleshoot problems or get hints.
  - Download [this playback extension](https://chrome.google.com/webstore/detail/vimeo-repeat-speed/noonakfaafcdaagngpjehilgegefdima/related?hl=en) to control playback speeds on Vimeo.
  - Download the [JSONView extension](https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc?hl=en) to view JSON better in your browser.

**Libraries:** Completing this project, requires the use of the [android-async-http](http://loopj.com/android-async-http/) and the [Picasso](http://square.github.io/picasso/) libraries. Add dependencies for these libraries to the [app/build.gradle](https://github.com/codepath/android-rest-client-template/blob/master/app/build.gradle#L30-L32) file.

**Submitting Assignments:** Submitted through Github, check out the [[Submitting Assignments|Submitting Assignments]] page for more details.

**README Template:** Be sure to **include a README** containing a GIF walkthrough of your app. Use [this README template](/snippets/{{COURSE | slug}}/readme_templates/project_2_readme.md?raw=true) in order to have a complete README.

**User Stories**:

The following user stories **must** be completed:

- User can enter a search query that will display a grid of image results from the Google Image API.
- User can click on "settings" which allows selection of advanced search options to filter results
- User can configure advanced search filters such as:
    - Size (_small, medium, large, extra-large_)
    - Color filter (_black, blue, brown, gray, green, etc..._)
    - Type (_faces, photo, clip art, line art_)
    - Site (_espn.com_)
- Subsequent searches will have any filters applied to the search results
- User can tap on any image in results to see the image full-screen
- User can [scroll down “infinitely”](http://guides.codepath.com/android/Endless-Scrolling-with-AdapterViews-and-RecyclerView) to continue loading more image results (up to 8 pages)

The following advanced user stories are **optional**:

- **Advanced:** Robust error handling, [check if internet is available](http://guides.codepath.com/android/Sending-and-Managing-Network-Requests#checking-for-network-connectivity), handle error cases, network failures
- **Advanced:** Use the [ActionBar SearchView](http://guides.codepath.com/android/Extended-ActionBar-Guide#adding-searchview-to-actionbar) or custom layout as the query box instead of an EditText
- **Advanced**: User can [share an image](http://guides.codepath.com/android/Sharing-Content-with-Intents) to their friends or email it to themselves
- **Advanced:** Replace Filter Settings Activity with a lightweight [modal overlay](http://guides.codepath.com/android/Using-DialogFragment)
- **Advanced:** Improve the user interface and experiment with image assets and/or styling and coloring
- **Bonus:** Use the [StaggeredGridView](https://github.com/f-barth/AndroidStaggeredGrid) to display improve the grid of image results
- **Bonus:** User can [zoom or pan images](https://github.com/MikeOrtiz/TouchImageView) displayed in full-screen detail view

**Cliffnotes:**

- (Cliffnotes) [Organizing your Source Files](http://guides.codepath.com/android/Organizing-your-Source-Files)
- (Cliffnotes) [Converting JSON to Models](http://guides.codepath.com/android/Converting-JSON-to-Models)
- (Cliffnotes) [Working with the Image View](http://guides.codepath.com/android/Working-with-the-ImageView)
- (Cliffnotes) [Configuring the ActionBar](http://guides.codepath.com/android/Defining-The-ActionBar)
- (Cliffnotes) [Using an ArrayAdapter](http://guides.codepath.com/android/Using-an-ArrayAdapter-with-ListView)
- (Cliffnotes) [Using Intents to Create Flows](http://guides.codepath.com/android/Using-Intents-to-Create-Flows)
- (Cliffnotes) [Sending Network Requests](http://guides.codepath.com/android/Sending-and-Managing-Network-Requests)
- (Cliffnotes) [Endless Scrolling a GridView](http://guides.codepath.com/android/Endless-Scrolling-with-AdapterViews-and-RecyclerView)

**References For This Assignment:**

- (API) [Google Image Search API Reference](https://developers.google.com/image-search/v1/jsondevguide#json_reference)
- (Guide) [Intent Android Docs](http://developer.android.com/guide/components/intents-filters.html)
- (Guide) [Accessing and Providing Resources](http://developer.android.com/guide/topics/resources/providing-resources.html)
- (Library) [Android Async HTTP Client](http://loopj.com/android-async-http/)
- (Library) [Picasso Image Downloader](http://square.github.io/picasso/)
- (Tutorial) [Intents Tutorial](http://www.vogella.com/articles/AndroidIntent/article.html)
- (Wiki) [Using an ArrayAdapter](http://guides.codepath.com/android/Using-an-ArrayAdapter-with-ListView)

**Mockups:**

With required user stories completed:

![Grid Image 1|280](google_image_1.png)
![Grid Image 2|280](google_image_2.png)
![Grid Image 3|280](google_image_3.png)

With several optionals completed, the app might look like:

![Grid Image 4|280](grid_image_1_extras.png)
![Grid Image 5|280](grid_image_3_extras.png)
![Grid Image 6|280](grid_image_2_extras.png)
