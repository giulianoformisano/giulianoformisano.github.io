---
layout: page
title: Teaching
permalink: /teaching/
---
<!-- Fresh copy request -->
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta http-equiv="cache-control" content="no-cache, no-store, must-revalidate">
<meta http-equiv="pragma" content="no-cache">
<meta http-equiv="expires" content="0">

<!-- This is the container where your teaching list will be automatically loaded -->
<div id="teaching-list">
  <!-- Loading content... -->
</div>

<script>
// This function fetches the latest content and updates the page
function loadTeachingContent() {
  // fetch() retrieves the content from your new file.
  // The '?' followed by a timestamp is added to prevent the browser from using a cached version.
  fetch('teaching-content.html?v=' + new Date().getTime())
    .then(response => {
      // Check if the request was successful
      if (!response.ok) {
        throw new Error('Network response was not ok');
      }
      return response.text();
    })
    .then(data => {
      // Place the fetched HTML content inside the 'teaching-list' div
      document.getElementById('teaching-list').innerHTML = data;
    })
    .catch(error => {
      // If there's an error (e.g., file not found), log it to the console
      console.error('Error fetching teaching content:', error);
      document.getElementById('teaching-list').innerHTML = '<p>Could not load content.</p>';
    });
}

// 1. Load the content as soon as the page is ready
document.addEventListener('DOMContentLoaded', loadTeachingContent);

// 2. Set the content to automatically refresh every 30 seconds (30000 milliseconds)
// You can change this interval to be longer or shorter.
setInterval(loadTeachingContent, 30000);
</script>
