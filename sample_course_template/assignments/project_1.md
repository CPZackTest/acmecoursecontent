## Week 1 Project: Instagram Photo Viewer

**Due:** {{PROJECT(1) | longdate}} at 10pm

**Overview**: Build a read-only photo viewer for Instagram which allows a user to check out popular photos.

**Guide**: Please review the @[[Weekly Projects Slide Deck|slides/Weekly Projects Overview.pdf]] for a more detailed visual guide for building this app.

**Walkthrough:** Check out the provided [video walkthrough](https://player.vimeo.com/video/105515674) for this project to get you started. Check the [Project 1 Tips Guide](#!hints) to troubleshoot problems or get hints.
  - Download [this playback extension](https://chrome.google.com/webstore/detail/vimeo-repeat-speed/noonakfaafcdaagngpjehilgegefdima/related?hl=en) to control playback speeds on Vimeo.
  - Download the [JSONView extension](https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc?hl=en) to view JSON better in your browser.

**Libraries:** Completing this project, requires the use of the [android-async-http](http://loopj.com/android-async-http/) and the [Picasso](http://square.github.io/picasso/) libraries. Add dependencies for these libraries to the [app/build.gradle](https://github.com/codepath/android-rest-client-template/blob/master/app/build.gradle#L24-L25) file.

**Submitting Assignments:** Submitted through Github, check out the [[Submitting Assignments|Submitting Assignments]] page for more details.

**README Template:** Be sure to **include a README** containing a GIF walkthrough of your app. Use [this README template](/snippets/{{COURSE | slug}}/readme_templates/project_1_readme.md?raw=true) in order to have a complete README.

**User Stories**:

The following user stories **must** be completed:

- User can scroll through current popular photos from Instagram
- For each photo displayed, user can see the following details:
  - Graphic, Caption, Username
  - (Optional) relative timestamp, like count, user profile image

The following advanced user stories are **optional**:

- **Advanced:** Add pull-to-refresh for popular stream with [SwipeRefreshLayout](http://guides.codepath.com/android/Implementing-Pull-to-Refresh-Guide)
- **Advanced:** Show latest comment for each photo (bonus: show last 2 comments)
- **Advanced:** Display each user profile image using a [RoundedImageView](https://github.com/vinc3m1/RoundedImageView)
- **Advanced:** Display a nice default placeholder graphic for each image during loading (read more about Picasso)
- **Advanced:** Improve the [user interface](http://guides.codepath.com/android/Styling-UI-Screens-FAQ#actionbar) through styling and coloring
- **Bonus:** Allow user to view all comments for an image within a separate activity or [dialog fragment](http://guides.codepath.com/android/Using-DialogFragment)
- **Bonus:** Allow video posts to be played in full-screen using the [VideoView](http://guides.codepath.com/android/Video-Playback-and-Recording#playing-local-video)

**Cliffnotes:**

- (Cliffnotes) [Android Directory Structure](http://guides.codepath.com/android/Android-Directory-Structure)
- (Cliffnotes) [Constructing View Layouts](http://guides.codepath.com/android/Constructing-View-Layouts)
- (Cliffnotes) [Populating a ListView Using Custom Adapter](http://guides.codepath.com/android/Using-an-ArrayAdapter-with-ListView)
- (Cliffnotes) [Working with ImageView](http://guides.codepath.com/android/Working-with-the-ImageView)
- (Cliffnotes) [Basic Event Handling](http://guides.codepath.com/android/Basic-Event-Listeners)
- (Cliffnotes) [Using Strings and other Resources](http://guides.codepath.com/android/Using-String-Resources)

**References For This Assignment**:

- (Guide) [App Fundamentals](http://developer.android.com/guide/components/fundamentals.html)
- (Guide) [Declaring Layouts](http://developer.android.com/guide/topics/ui/declaring-layout.html)
- (Guide) [LinearLayout](http://developer.android.com/guide/topics/ui/layout/linear.html)
- (Guide) [RelativeLayout](http://developer.android.com/guide/topics/ui/layout/relative.html)

**Mockups**

With required user stories completed and a basic scrolling feed of popular photos:

![Instagram 1|320](instagram_1.png)

With several optionals and enhanced feed of popular photos:

![Instagram 4|320](instagram_4.png)
![Instagram 3|320](instagram_3.png)
