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
  const url = 'https://giulianoformisano.github.io/home-content.html?v=' + Date.now();

  fetch(url)
    .then(response => {
      if (!response.ok) throw new Error("Couldn't load homepage");
      return response.text();
    })
    .then(html => {
      document.getElementById('homepage-content').innerHTML = html;
    })
    .catch(error => {
      console.error(error);
      document.getElementById('homepage-content').innerHTML =
        "<p>Could not load homepage.</p>";
    });
}

document.addEventListener('DOMContentLoaded', loadHomepage);

// Optional auto-refresh
setInterval(loadHomepage, 30000);
</script>
