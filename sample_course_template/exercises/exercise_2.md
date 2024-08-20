## Week 2 Lab Exercises

### Topics in Focus

While there are many topics covered each week, the topics in focus are the ones that require deeper experimentation. This week the topics are:

* Actions: [ActionBar](http://guides.codepath.com/android/Defining-The-ActionBar), [Toolbar](http://guides.codepath.com/android/Using-the-App-ToolBar)
  * Explore the differences between ToolBar and ActionBar
  * Explore the use of "promoted actions" with [Floating Action Button](https://guides.codepath.com/android/Floating-Action-Buttons)
  * Explore [extended actions](http://guides.codepath.com/android/Extended-ActionBar-Guide) with `SearchView`, `ActionView`, `ShareProvider` and more
* Intents: [Explicit Intents](http://guides.codepath.com/android/Using-Intents-to-Create-Flows), [Implicit Intents](http://guides.codepath.com/android/Common-Implicit-Intents)
   * Explore how to pass complex data [using Parcelable](https://guides.codepath.com/android/Using-Parcelable)
   * Understand the [navigation task stack](http://guides.codepath.com/android/Navigation-and-Task-Stacks) 
   * Intents are messages used to communicate between apps / components
   * Explore implicit intents. What makes them so powerful? (Turns apps into libraries)

### Challenge

This week we will be playing with ActionBar, SearchView and Intents. We will be doing this challenge in pairs during the lab. There will be about an hour allotted for development.

The app is composed of two screens. The first screen displays a list of books, in which, each book is described by its title, author and cover photo. After a user selects a book from the list, a second screen appears displaying additional details about the book, including the publisher and no. of pages.

**Book List :**

![Imgur](http://i.imgur.com/sSINs2zl.png)

**Book Details :**

![Imgur](http://i.imgur.com/y9a4AtQl.png)

### Objectives

1. How to access a typical RESTful API?
2. How to parse JSON results and understand JSON format?
3. How to add SearchView to ActionBar to search books?
4. How to use explicit and implicit intents?
5. How to communicate data between apps using intents?
6. How to share remote images?
7. How to use ProgressBar?

### Goal

Pair up and build a book search app that searches the [OpenLibrary API](https://openlibrary.org/developers/api) to search books by author or title.

* Display the list of books with its cover images.
* Use SearchView to search for books.
* Add a detail view to display more information about the selected book from the list.
* Use a share intent to recommend books to friends.
* Show ProgressBar before network request.


1. Import base app
  * The app connects to the OpenLibrary API and displays a list of books. You will be building new features on top of this app.
  * Clone [android-booksearch-exercise repo](https://github.com/codepath/android-booksearch-exercise) on your machine. Import the project in Android Studio:

    ![Import|600](http://i.imgur.com/joPKoTk.gif)

2. Test your app
  * Test to verify that the app runs without any errors.
  * If your app loads successfully, you should see the following output:

    ![Screenie|300](http://i.imgur.com/NJmF42Yl.png)
  * If you receive a `SocketTImeoutError` you'll need to increase the timeout duration for the `AsyncHttpClient` in the `BookClient` class.

    ```java
    // in BookClient.java
    public BookClient() {
        this.client = new AsyncHttpClient();
        client.setTimeout(20 * 1000); // Increase default timeout
    }
    ```

3. Add SearchView to ActionBar
  * The app should allow you to search for books by its author or title. One of the preferred ways to do this is by using a SearchView.
  * Refer [adding SearchView to ActionBar](http://guides.codepath.com/android/Extended-ActionBar-Guide#adding-searchview-to-actionbar) guide for more details.
  * Make sure to **remove the call** to `fetchBooks("Oscar Wilde")` from the `onCreate()` method in `BookListActivity` before testing the `SearchView`.

    ```java
    // Remove this call in BookListActivity#onCreate
    fetchBooks("Oscar Wilde");
    ```
  * Instead, place the `fetchBooks()` call in the appropriate place to allow the user's search query to populate the list.

4. Hook up Book Detail View
  * You will find `BookDetailActivity.java` and it's layout file `activity_book_detail.xml` in your project to display more information about the book selected from the list.
      * This activity is used to show book title, author and cover image.
  * Setup an item click listener for the list of books
  * Fire an intent when the user selects a book from the list
  * Pass the book through the intent and populate the detail view
  * Ensure the book object is able to be marshalled by implementing [Parcelable](http://guides.codepath.com/android/Using-Parcelable#creating-a-parcelable-the-easier-way-using-intellij-or-android-studio).
  * You can install the [parcelable plugin](https://github.com/mcharmas/android-parcelable-intellij-plugin) to make creating a Parcelable easier.
  * Refer [Using Intents to Create Flows](http://guides.codepath.com/android/Using-Intents-to-Create-Flows) cliffnotes for guidelines on passing data between activities.
  * Change activity title to reflect the book title by referring to the [Configuring The ActionBar](http://guides.codepath.com/android/Defining-The-ActionBar#changing-the-actionbar-icon-or-title) guide.
  * **(Bonus)** Get additional book information like publisher and pages count from the [Books API](https://openlibrary.org/dev/docs/api/books) and display in details view.

5. Add Share Intent
  * Add a `ShareActionProvider` to the ActionBar of `BookDetailActivity` so you can share the book image to other apps.
  * Share the cover image by referring to [sharing remote images](http://guides.codepath.com/android/Sharing-Content-with-Intents#shareactionprovider) guide.
  * **(Bonus)** Share book title and cover image using the same intent.

6. Show Progress Bar
  * Display a ProgressBar while the book data is being fetched and hide it once the data is loaded in the ListView.
  * Refer to the [implementing progress guide](http://guides.codepath.com/android/Handling-ProgressBars#progress-within-actionbar) guide to show and hide an indeterminate progressbar.

7. Run and test your app.

### Concept Review

* What is context? When it is used? Why?
* How do I setup a click handler for items in a ListView?
* How do I change the title text in the ActionBar? How do I add menu items?
* How can I make menu items clickable?
* What is an intent? What are the two types and how do they differ?
* What types of tasks can I do with an implicit intent?
* How do I communicate data between intents? to a child intent and back to the parent?
* How do I enable an arbitrary object to be passable via an intent?

### Additional Optional Exercises

There are a series of exercises you **optionally** can perform to **review the concepts** introduced this week:

- [Chapter 4: Interaction Exercises](http://codepath.github.io/intro_android_exercises/chapters/chapter04.html)
- [Chapter 5: Intent Exercises](http://codepath.github.io/intro_android_exercises/chapters/chapter05.html)

These are in addition to the mini-projects and are not required but are supplemental content.
