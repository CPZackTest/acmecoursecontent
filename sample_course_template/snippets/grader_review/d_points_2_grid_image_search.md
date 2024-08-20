## Week 2: Grid Image Search

### Did they re-use a single method for sending out network requests for all cases?

**YES**

* Properly reused the single base method in search activity to fetch results for both initial load and the pagination

**NO**

* Consider cleaning up your search activity such as re-using a single method for both initial load and pagination

### Did they pass the correct pagination parameter into the API call?

**NO**

* Your pagination is **incorrect** because "start" param is an **offset rather than page** i.e 0, 8, 16

### Did they put the grid image search input field into the ActionBar?

**YES**

* Nice to see you added the search box to the ActionBar!

**NO**

* Consider moving the search field into the ActionBar using a [custom ActionBar layout](http://guides.codepath.com/android/Extended-ActionBar-Guide#custom-actionbar-layout) or with a [SearchView](http://guides.codepath.com/android/Extended-ActionBar-Guide#adding-searchview-to-actionbar)

### Did they properly setup spinners on the settings page with filter options?

**YES**

* Properly used spinners (with populated values) to allow users to select filters

### Did they properly pass spinner values back to the search activity after submission?

**YES**

* Properly sent and received relevant filters using a bundle to pass data between activities

OR

* Nice work setting up shared preferences to persist the settings between activities

### Did they create an object that encapsulates all the filter fields?

**YES**

* Good to see you used a filters object to represent the filters to apply to the query

**NO**

* One thing to consider is rather than sending and returning all the filter values separately as keys, might have introduced a serializable model (i.e `SearchFilters.java`) representing all the filters which were passed back and forth between activities within the bundle.

### Did they add then optional task of allowing users to share the image via the share intent?

**YES**

* Nice job adding the share intent to the image detail view!

**NO**

* Consider adding the ability to [share an image](http://guides.codepath.com/android/Sharing-Content-with-Intents). This is an important learning for this assignment even though it's optional.