---
layout: page
title:
permalink: /
---

<div id="homepage-content">
  <p>Loading...</p>
</div>

<script>
function loadHomepage() {
  const url = '{{ "/index-content.html" | relative_url }}?v=' + Date.now();

  fetch(url)
    .then(response => {
      if (!response.ok) {
        throw new Error("Couldn't load homepage content.");
      }
      return response.text();
    })
    .then(html => {
      document.getElementById('homepage-content').innerHTML = html;
    })
    .catch(error => {
      console.error("Error loading homepage:", error);
      document.getElementById('homepage-content').innerHTML =
        "<p>Could not load homepage content.</p>";
    });
}

document.addEventListener('DOMContentLoaded', loadHomepage);
</script>
