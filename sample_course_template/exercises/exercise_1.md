## Week 1 Lab Exercises

### Topics in Focus

While there are many topics covered each week, the topics in focus are the ones that require deeper experimentation. This week the topics are:

* Layouts: [RelativeLayout](https://guides.codepath.com/android/Constructing-View-Layouts#relativelayout), [PercentRelativeLayout](https://guides.codepath.com/android/Constructing-View-Layouts#percentrelativelayout)
  * Explore the different relational rules
  * Explore how position and alignment can be used to determine widths and heights
  * Explore how to properly constrain your views on each edge
* Lists: [Row Recycling](http://guides.codepath.com/android/Using-an-ArrayAdapter-with-ListView#row-view-recycling), [ViewHolder](http://guides.codepath.com/android/Using-an-ArrayAdapter-with-ListView#improving-performance-with-the-viewholder-pattern)
  * Explore the adapter pattern and how each element fits together
  * Explore view recycling and how to re-use. What is `convertView`?
  * What is the `ViewHolder` pattern? Why is this important?
  * Explore how `ListView` differs from the newer [RecyclerView](http://guides.codepath.com/android/Using-the-RecyclerView)

### Challenge

This week we will be playing with how to layout views and style user interfaces. We will be doing this challenge in pairs during the lab. There will be about 1 1/2 hours allotted for development.

![Login Screen|250](http://i.imgur.com/sCIXqp3.png)
![Stream|250](http://i.imgur.com/1ly82h6.png)

1. Create New Project
  * Create a new android project (minSDK 16) and choose to create a "Blank Activity"
  * Name the new blank activity as "LoginActivity"
2. Clone Login Screen
  * Browse [Login Screens](https://pttrns.com/android-patterns?scid=17) on Android App Patterns
  * Recreate one chosen login screen as closely as possible while using android views and layouts
  * Use real text fields, layouts, buttons where possible. Don't just copy one big screenshot
  * The goal is to clone the **structure and layout of the screen** but you can find other images or borrow from the reference implementation
  * When pressing sign in, hook up the button event to toast (or take you to the stream screen below)
  * You can use nested layouts to achieve more complicated configurations
  * **Review:** [Styling UI Screens FAQ](http://guides.codepath.com/android/Styling-UI-Screens-FAQ), [Working with ImageView](http://guides.codepath.com/android/Working-with-the-ImageView#scale-types), [Cloning Login Screen](http://guides.codepath.com/android/Cloning-a-Login-Screen-Layout-Guide)
  * **Tip:** Use a color picker to help get the exact RGB value (Windows: [Pixeur](http://pixeur.en.softonic.com/) or Mac: [Sip](https://itunes.apple.com/us/app/sip/id507257563?mt=12))

3. **(Bonus)** Clone Stream View
  * Browse [Stream Screens](https://pttrns.com/android-patterns?scid=11) on Android App Patterns
  * Recreate one chosen stream screen as closely as possible while using android views and layouts
  * The data is faked but focus on recreating the items within the stream as closely as possible to the reference implementation.
  * **Review:** [Styling UI Screens FAQ](http://guides.codepath.com/android/Styling-UI-Screens-FAQ)

### Concept Review

* Most common screens in most mobile apps? (Login, Feed, Detail, Create Form)
* What is an activity? What are the two key files to any Activity?
* Describe the method by which items are populated into list, what steps are needed?
* How do you improve the performance of a ListView? What exactly does the ViewHolder pattern do?
* Describe exactly what an adapter is? How does the getView method work?
* Why do we need string resources? How do we use them? What other resource types have we used?
* How does positioning with RelativeLayout work? What types of rules can I apply?
* What are the different ways to add spacing between view elements?
* What are the most common view elements used in app?

### Additional Optional Exercises

There are a series of exercises you **optionally** can perform to **review the concepts** introduced this week:

- [Chapter 1: Fundamental Exercises](http://codepath.github.io/intro_android_exercises/chapters/chapter01.html)
- [Chapter 2: Layout Exercises](http://codepath.github.io/intro_android_exercises/chapters/chapter02.html)
- [Chapter 3: View Exercises](http://codepath.github.io/intro_android_exercises/chapters/chapter03.html)

These are in addition to the mini-projects and are not required but are supplemental content.
