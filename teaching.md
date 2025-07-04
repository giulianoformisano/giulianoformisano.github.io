---
layout: page
title: Teaching
permalink: /teaching/
---
<!-- This container will be filled with your teaching list -->
<div id="teaching-list">
  <p>Loading teaching schedule...</p>
</div>

<script>
function loadTeachingContent() {
  // Use the full GitHub Pages URL to fetch your content file.
  // The timestamp at the end helps prevent the browser from using an old, cached version.
  const contentUrl = 'https://giulianoformisano.github.io/teaching-content.html?v=' + new Date().getTime();

  fetch(contentUrl)
    .then(response => {
      // If the response is not 'ok' (e.g., a 404 "Not Found" error), stop here.
      if (!response.ok) {
        throw new Error('Network response was not ok. Check if the URL is correct.');
      }
      return response.text();
    })
    .then(htmlContent => {
      // Success! Place the fetched content into the div.
      document.getElementById('teaching-list').innerHTML = htmlContent;
    })
    .catch(error => {
      // If anything goes wrong, display an error message in the container.
      console.error('Error fetching teaching content:', error);
      document.getElementById('teaching-list').innerHTML = '<p>Could not load content. Please check the file URL.</p>';
    });
}

// 1. Load the content as soon as the page is ready.
document.addEventListener('DOMContentLoaded', loadTeachingContent);

// 2. Set the content to automatically refresh every 30 seconds (30000 milliseconds).
setInterval(loadTeachingContent, 30000);
</script>
