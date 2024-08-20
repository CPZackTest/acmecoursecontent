## Week 3 - Common Questions

### Lecture Questions

#### How do I import an existing Android Studio project correctly?

See the [Importing existing Android Studio projects](http://guides.codepath.com/android/Getting-Started-with-Gradle#importing-existing-android-studio-projects) guide.  It also
contains more context about the [Gradle](http://guides.codepath.com/android/Getting-Started-with-Gradle#intro-to-gradle) dependency management system.

#### Will I ever use AsyncTask?

Most libraries you used in this class will handle the threading work for you.  However, if you ever intend to go fix an issue in open source, it's likely
you need to understand the threading model behind Android.  It's also important to know so you don't commit an interview mistake by putting networking I/O
on the main thread.

#### Are there any ways to inspect my SQLLite database?

If you want to see what's currently stored in your SQLLite table, you either need to set a breakpoint and do queries inside the debugger.  Or you need
to go to `Tools`->`Android Device Monitor`->`File Explorer` and look inside the `/data/<app package name>/databases` and download the file locally
to inspect the tables using a tool such as [DB Browser for SQLite](http://sqlitebrowser.org/).

#### Why is there an option to turn off making network requests on the main thread?

Early Android versions didn't have this restriction, so a lot of apps would block on network I/O and often create poor user experiences.  Google eventually
started enforcing this [StrictMode](http://developer.android.com/reference/android/os/StrictMode.html) policy starting in Android v3.0.  To provide backwards compatibility
for older apps that did block and would cause crashes, this option was provided.  However, you should in general never disable it.

#### Is Active Android or SQLiteOpenHelper using AsyncTask?

No, but anything that blocks the main thread for a long duration should be moved to take advantage of it.

### How would I implement retry mechanisms?

We'll talk about [Background Services](http://guides.codepath.com/android/Starting-Background-Services) in more detail in Week 8.

### Group Project Questions

#### For the group project, are people going to have to separate back-end and front-end responsibilities?

We're going to have you work with [Parse](http://guides.codepath.com/android/Building-Data-driven-Apps-with-Parse) so the need to build out API's, configuring and maintaining databases, and buiding out infrastructure such as push notifications outside the Android world can be minimized.  You should be focused on building out the major [Mobile Screen Archetypes](http://guides.codepath.com/android/Mobile-Screen-Archetypes) and apply what you've learned from this class.

#### How much time will I have to build this group project?

You will start wireframing during the 4th week and will then be implementing the app in three week-long development sprints with your team.
