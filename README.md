# Tourist Bureau Workshop

You will build a website for the local visitor's bureau that will help tourists explore all the things to do in the area. If they find an excursion they like, they can buy "e-tickets" directly from the site.

**Be sure to look at previous projects for inspiration**

## Home Page (required)

A home page with informational text/images promoting the town and navigation links
to the other pages. It needs a professional, but minimalistic appearance. Their budget
for this project is tiny!

Requirements: 
- **Display a dropdown list of the provided categories to the user**
    - Add a `<select>` to the `activities.html` with a matching `id` and `name` property do display the categories
    - In `scripts/activities.js` write code that generates options for the categories `<select>` using the data in the `categories` array provided. Use the activity for the `textContent` and `value` for each option you generate.
    - Be Sure to include a default option that says **Select an Activity** with an empty string as it's value.
    - Make a commit

- **When a category is selected, display a dropdown of matching activities**
    - Add a `<select>` to the `activities.html` with a matching `id` and `name` property to display the activities for the selected category
    - In `scripts/activities.js` listen for the change event on the categories dropdown created above using `addEventListener` in the `window.onload` function. 
    - Create a function that is called with the event listener that finds the matching activies in the provided `activites`.
    - Write code that generates options for the actities `<select>` from the activies that match the selected category. Use the `name` property for the `textContent` and the `id` property `value` for each option you generate. 
    - Be Sure to include a default option that says **Select an Activity** with an empty string as it's value.

    **Here are some functions that will help**  
    ```js

    //This function will hide or show an HTML element on the page
    //Just pass it the id of the element you want to show/hide
    function hideOrShowElement(someElementsID) {
        let el = document.getElementById(someElementsID);
        if (el.style.display === "none") {
            el.style.display = "block";
        } else {
            el.style.display = "none";
        }
    }

    ```

    ```js

    //This funciton will return a a list of the matching activities for a given category
    //Just pass it the array of activities and the category you are looking for
    function getActivitiesInCategory(activities, category) {

        //start by creating an empty list to hold our matches
        let matching = [];
        //number of items on the menu
        let numItems = activities.length;

        //loop over the activities to find matches
        for (let i = 0; i < numItems; i++) {
            if (activities[i].category === category) {
                //add that activity to our matches
                matching.push(activities[i]);
            }
        }
        
        //return all the matching menu items
        return matching;
    }


    //Example usage
    let matches = getActivitiesInCategory(activities, "Adventures"); 

    ```
