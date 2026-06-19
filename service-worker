const CACHE_NAME = "eccv-calculator-v1";

const urlsToCache = [
  "./",
  "./index.html",
  "./unit.html",
  "./js/all.min.js"
];

self.addEventListener("install", event => {
  event.waitUntil(
    caches.open(CACHE_NAME)
      .then(cache => cache.addAll(urlsToCache))
  );
});

self.addEventListener("fetch", event => {
  event.respondWith(
    caches.match(event.request)
      .then(response => {
        return response || fetch(event.request);
      })
  );
});
