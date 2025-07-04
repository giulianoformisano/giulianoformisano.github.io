---
layout: page
title: Research
permalink: /research/
---
<!-- This is the container where your research list will be loaded -->
<div id="research-list">
  <p>Loading research portfolio...</p>
</div>

<script>
function loadResearchContent() {
  // IMPORTANT: Replace the URL below with the URL for your new research-content.html file.
  const contentUrl = 'https://giulianoformisano.github.io/research-content.html?v=' + new Date().getTime();

  fetch(contentUrl)
    .then(response => {
      if (!response.ok) {
        throw new Error('Network response was not ok. Check the file URL.');
      }
      return response.text();
    })
    .then(htmlContent => {
      // Place the fetched content into the 'research-list' div
      document.getElementById('research-list').innerHTML = htmlContent;
    })
    .catch(error => {
      console.error('Error fetching research content:', error);
      document.getElementById('research-list').innerHTML = '<p>Could not load research content.</p>';
    });
}

// 1. Load the content when the page is first opened.
document.addEventListener('DOMContentLoaded', loadResearchContent);

// 2. Set the content to automatically refresh every 30 seconds.
setInterval(loadResearchContent, 30000);
</script>
