## Week 2 - Common Questions

### Should I implement my listeners at compile-time or define inside XML?  What about for the menu options?

Define at XML if possible, though be careful of defining your methods if you declare in the XML. For the ActionBar, use the `onOptionsItemSelected()` method already provided.

### How do you know if you’re implementing the support library ActionBar?

When an Activity is extended from `AppCompatActivity` (or `FragmentActivity`) instead of `Activity` we are using the support library.

### Why do I need multiple request codes?

So you can distinguish between payload that are returned by different child activities (i.e. create vs. settings screen)

### What’s `getBaseContext()?`

Don’t use it - it creates a lot of strange behavior. Use the activity context (`this`) whenever possible.

### How does the support library affect my themes?

The support library requires the use of `Theme.AppCompat` or a variant such as `Theme.AppCompat.Light.DarkActionBar` to be set as the parent theme within `res/values/styles.xml`. This is because the compatibility theme is required to properly display new things such as the `ActionBar` within the older phones.

### When do I need to use super() to call parent methods such as `onCreate()`?

In Android Studio, try using `Navigate` -> `Declaration` over these line statements.  If you use the SDK Manager and install the Android source code for the particular API
version you're building, you can study which ones actually matter.  In Java, the constructor is [not inherited](http://stackoverflow.com/questions/1644317/java-constructor-inheritance) so `super()` is necessary in those cases.

### What’s the difference between targetSDK and minSDK?

`android:minSdkVersion` is the minimum required API level to run an android app. If we will install the same app on lower API version the parser error will be appear, and application not support problem will appear. The Play Store will not allow an app to be installed beneath the minSDK value.

`android:targetSdkVersion` which indicates to the app that this was explicitly tested to work with the version specified here. Specifying this target version allows the platform to disable compatibility settings that are not required for the target version but may be required for older devices.

### Do I really need the support library?

Yes, because there are specific Lollilop features that are only supported if you use the support library such as `ViewPager`, `ToolBar`, `RecyclerView`, et al.

### What versions should I support?

It depends on your target market.  See the [Android dashboard](https://developer.android.com/about/dashboards/index.html) for a breakdown of versions across the installed base.
