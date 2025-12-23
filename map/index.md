---
title: Map
layout: default
---

<h1>Map</h1>
<p>Places I’ve been so far.</p>

<div id="map" style="height: 500px;"></div>

<link
  rel="stylesheet"
  href="https://unpkg.com/leaflet/dist/leaflet.css"
/>
<script src="https://unpkg.com/leaflet/dist/leaflet.js"></script>

<script>
  const map = L.map('map').setView([20, 0], 2);

  L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '© OpenStreetMap'
  }).addTo(map);

  const places = [
    {
      name: "Iceland",
      coords: [64.9631, -19.0208],
      url: "/travel/2025-08-10-iceland.html"
    },
    {
      name: "Alps",
      coords: [46.8876, 9.6570],
      url: "/travel/2025-09-02-alps.html"
    }
  ];

  places.forEach(place => {
    L.marker(place.coords)
      .addTo(map)
      .bindPopup(`<a href="${place.url}">${place.name}</a>`);
  });
</script>
