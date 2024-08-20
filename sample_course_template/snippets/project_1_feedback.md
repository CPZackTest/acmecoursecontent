## Project 1: Instagram Client Feedback

This is the feedback guide for Project 1 - Instagram Client.

 * **Did you name your Java activity semantically?** Your Java Activity should have a name like `PhotosActivity` with the `Activity` suffix.

 * **Did you name your XML Layout file properly?** Your XML Layout should have a name such as `activity_photos.xml` that matches the name of your Java class.

 * **Did you properly name your views?** Every view in your layout XML file should have a proper id that semantically describes the purpose AND have a prefix indicating the view type. For example, the text field where you show the caption might be called `tvCaption`. `tv` indicates this is a `TextView`.

 * **Did you use relative sp / dp for any view units?** All units within XML layouts should be relative using `sp` for font sizes and `dp` for margin+padding and any other positioning. You should also use `wrap_content` and `match_parent` for width/height whenever possible. Check out this [stackoverflow answer](http://stackoverflow.com/questions/2025282/difference-between-px-dp-dip-and-sp-in-android) for more detail about these units. Avoid ever using px or pt in Android apps.

 * **Did you properly apply relative placement rules in a RelativeLayout?** Learning RelativeLayout rules is one of the most important parts of learning about Android views. Switch to the XML view for your activity layout and notice the rules that are applied to position your views. Read more about this in our [RelativeLayout Cliffnotes](http://guides.codepath.com/android/Constructing-View-Layouts#relativelayout).

 * **Did you use string resources for your text?** In Android, you should always use string resources for your text rather than hardcoding string values in your layout files. See our [using string resources](http://guides.codepath.com/android/Using-String-Resources) for more details.

 * **Did you properly handle exceptions?** When making network requests, its very important to handle error cases and take appropriate actions when the network request fails. For this reason, it is always advisable to override the `onFailure` method in `JsonHttpResponseHandler` to handle the failures appropriately.
 
 * **Did you fix the ugly white space above and below the images displayed in the feed?** In certain cases you will likely notice ugly space that is above and below the image. This is due to not properly configuring the way the [ImageView is being rendered](https://guides.codepath.com/android/Working-with-the-ImageView#scale-types). Check the helpful hints guide and play with `scaleType` and setting the image's width and height to avoid this issue.

### Bonus

In addition, consider the following bonus (optional) feedback:

* **Could you improve the UX?** In all of these assignments, there are key places where you have the opportunity to improve the UI and UX of these projects. For example, it would be nice if you thought about updating the image to be displayed with the same proportions as on Instagram.

* **Could you improve the UI?** Learning to [improve UI](http://guides.codepath.com/android/Styling-UI-Screens-FAQ) is one of the most important aspects of learning about Android. It would be nice if you added proper margins, padding for your views. You may also notice the difference by formatting the text in your app. These  details are technically not as challenging, but adds a lot of polish to your finished app.

* **Did you make use of the ViewHolder pattern to improve performance?** ViewHolder is a pattern used for avoiding the calling of `findViewById` every time the `getView()` method is called. Imagine that you have a list with hundreds of rows, the `findViewById` will be called hundreds of times and it's not necessary, just bad for performance. So to increase the performance try to use the [ViewHolder pattern](http://guides.codepath.com/android/Using-an-ArrayAdapter-with-ListView#improving-performance-with-the-viewholder-pattern) as much as possible.

* **Did you implement pull-to-refresh for popular stream?** [Pull-to-refresh](http://guides.codepath.com/android/Implementing-Pull-to-Refresh-Guide#using-swiperefreshlayout) allows a user to refresh a list by pulling down and releasing from the top of the list. It makes it easier for users to load recently added items to the stream. Using [SwipeRefreshLayout](http://guides.codepath.com/android/Implementing-Pull-to-Refresh-Guide#using-swiperefreshlayout) is the easiest and most efficient way to achieve this.

* **Did you try to display comments on each post within the list?** Displaying comments can be an interesting addition to your project and will teach you quite a bit about how to create comments within a list item. See Tip #10 in the project hints on the courses portal for more details of how to achive this.