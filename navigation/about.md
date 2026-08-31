---
layout: post
title: About
permalink: /about/
comments: true
---

## As a conversation Starter

Here are some places I have visited before.

<comment>
Flags are made using Wikipedia images
</comment>

<style>
    /* Style looks pretty compact, 
       - grid-container and grid-item are referenced the code 
    */
    .grid-container {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(150px, 1fr)); /* Dynamic columns */
        gap: 10px;
    }
    .grid-item {
        text-align: center;
    }
    .grid-item img {
        width: 100%;
        height: 100px; /* Fixed height for uniformity */
        object-fit: contain; /* Ensure the image fits within the fixed height */
    }
    .grid-item p {
        margin: 5px 0; /* Add some margin for spacing */
    }

    .image-gallery {
        display: flex;
        flex-wrap: nowrap;
        overflow-x: auto;
        gap: 10px;
        }

    .image-gallery img {
        max-height: 150px;
        object-fit: cover;
        border-radius: 5px;
    }
</style>

<!-- This grid_container class is used by CSS styling and the id is used by JavaScript connection -->
<div class="grid-container" id="grid_container">
    <!-- content will be added here by JavaScript -->
</div>

<script>
    // 1. Make a connection to the HTML container defined in the HTML div
    var container = document.getElementById("grid_container"); // This container connects to the HTML div

    // 2. Define a JavaScript object for our http source and our data rows for the Living in the World grid
    var http_source = "https://upload.wikimedia.org/wikipedia/commons/";
    var living_in_the_world = [
        {"flag": "9/99/Flag_of_the_Philippines.svg", "Rating": "4", "description": "Philippines - I wasn't born here but visited as a baby"},
        {"flag": "2/24/Flag_of_the_Kingdom_of_Spain.svg", "Rating": "3", "description": "Spain - I visited here with my parents"},
        {"flag": "a/a8/Flag_of_Portugal_%28official%29.svg", "Rating": "2", "description": "Portugal - I visited here along with Spain"},
        {"flag": "e/ef/Flag_of_Hawaii.svg", "Rating": "1", "description": "Hawaii - I visited here a long time ago"},
    ];

    // 3a. Consider how to update style count for size of container
    // The grid-template-columns has been defined as dynamic with auto-fill and minmax

    // 3b. Build grid items inside of our container for each row of data
    for (const location of living_in_the_world) {
        // Create a "div" with "class grid-item" for each row
        var gridItem = document.createElement("div");
        gridItem.className = "grid-item";  // This class name connects the gridItem to the CSS style elements
        // Add "img" HTML tag for the flag
        var img = document.createElement("img");
        img.src = http_source + location.flag; // concatenate the source and flag
        img.alt = location.flag + " Flag"; // add alt text for accessibility

        // Add "p" HTML tag for the description
        var description = document.createElement("p");
        description.textContent = location.description; // extract the description

        // Add "p" HTML tag for the rating
        var rating = document.createElement("p");
        rating.textContent = location.rating;  // extract the rating

        // Append img and p HTML tags to the grid item DIV
        gridItem.appendChild(img);
        gridItem.appendChild(description);
        gridItem.appendChild(rating);

        // Append the grid item DIV to the container DIV
        container.appendChild(gridItem);
    }
</script>

### Journey through Life

- Before I went to Del Norte I used to go to a Catholic School named St. Michaels
- St. Michaels provided my elementary and middle school life
- Since 1st grade I have been playing piano with my teacher, I am still not the best
- During this time I also went to a coding school that was outside of St. Michaels
- I also became a Boy Scout during middle school, which I am still continuing for Eagle
- Then I came to Del Norte where I am now

### Culture, Family, and Fun

I was born on June 8, 2010 and I have 5 brothers. I live in California and I frequently talk to my extended family.

- Both of my parents are Philippino and they moved here when they were about my age.
- My family loves to hold big parties with the whole extended family whether it be for a     holiday or another occation, like sports.

<comment>
Gallery of Pictures
</comment>
<div class="image-gallery">
  <img src="{{site.baseurl}}/images/about/Family.jpeg" alt="Image 1">
  <img src="{{site.baseurl}}/images/about/Deer.jpeg" alt="Image 2">
  <img src="{{site.baseurl}}/images/about/Graduation.jpeg" alt="Image 3">
  <img src="{{site.baseurl}}/images/about/Bowling.jpeg" alt="Image 4">
  <img src="{{site.baseurl}}/images/about/AnotherDear.jpeg" alt="Image 5">
  <img src="{{site.baseurl}}/images/about/Helmet.jpeg" alt="Image 6">
</div>
