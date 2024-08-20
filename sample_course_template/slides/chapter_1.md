# 1. App Fundamentals
## Understanding Android Applications

---

# Library vs Framework

What is the difference between a library and a framework?

**Libraries** are called by your code.<br/>
**Frameworks** calls your code. 

Android is a framework for building mobile applications.

---

# ￼Android Source

An android app has a very specific folder structure, with all code organized into a particular pattern:

* src - This is where all Java source files are located
* lib - This is where third-party libraries are stored
* res/layout - XML defining view layouts
* res/drawable - Place to store images
* res/values - Strings, colors, etc
* assets - Place to store misc. static files (i.e text files)
* gen - Automatically generated read-only code
* AndroidManifest.xml - Application-wide se￼￼￼ttings

---

# ￼￼Android Manifest

AndroidManifest.xml is in every android application and contains application-wide settings.

The manifest specifies:

*  Package and application name
*  What the application launches on startup
*  The components and views of the application
*  Permissions the app requires
*  The version of android the app targets

---

# ￼Fundamentals Exercises 1

* Open HelloWorldDemo in Android Studio
* Open AndroidManifest.xml
  * Change the version code and name to 2 and 2.0
  * Change the application icon
  * Change the application name

---

# ￼￼Activity

In Android, each full-screen within an application is called an Activity.

 * An application can have one or more activities that make up the interaction flow.
 * Activities have at least two parts:
   * The Java source file in `src/package/FooActivity.java`
   * The XML layout in `res/layout/foo_activity.xml`
 * Activities are each independent and do not directly communicate with each other.


---

# ￼￼Activity Source

This is how an activity looks:

```java
public class MainAcivity extends ActionBarActivity {
   public void onCreate(Bundle savedInstanceState) {
      super.onCreate(savedInstanceState);
      // Inflating the layout file from res/layout/activity_main.xml
      setContentView(R.layout.activity_main);
   }

  // other methods here
}
```

---

## ￼￼Resources

In Android, Resources include strings, images, colors, xml-based activity layouts, menu items, etc.

* In XML, resources are access by a special syntax
   * `@string/my_string` - references string in `strings.xml`
   * `@drawable/cool_image` - references image in drawable folder.

* In Java, at compile time the resources folders are inspected and a special class called R is **generated**.
  ```java
  R.string.my_string
  ```

---

# ￼￼Strings

In Android, Strings are typically not hard-coded in your application but instead stored in strings.xml

  * The `strings.xml` file is used to define a key "name" for the string and the value which is the text.
  * You can access strings as `@string/some_name` (XML) or `R.string.some_name` (Java)

```xml
<resources>
    <string name="some_name">My String Text</string>
</resources>
```

---

# ￼￼Activity Lifecycle

An Android activity transitions through various states as it is shown, hidden, and destroyed.

* Each state transition will call a method on the Activity.
* The three most important methods are:
  * `onCreate` - Called to create an activity. Usually sets the xml layout to use as the interface.
  * `onPause` - Called when leaving an activity. Usually where any needed data is stored for later.
  * `onResume` - Called when returning to an activity. Any stored data is restored here.

---

## ￼￼Fundamentals Wrap-up

 * Each Android project has several key folders including res and src.
 * The AndroidManifest.xml is a file which stores all application settings and configuration.
 * Every full-screen on the Android is called an Activity. An application typically has multiple activities.
 * Android development involves access to many resources including strings, colors, layouts, et al.
 * Activities have a lifecycle which can be managed using methods such as onCreate
 * For position, dp relative units are used. For text size, we ￼￼use sp.
