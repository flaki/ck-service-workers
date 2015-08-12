# Service Worker
## Use cases

---

---

### Service workers are a lot of things

---

---

# Offline

* Offline webapps
* Replacing AppCache
* More control, less surprises
* "Scriptable proxy"

> This is probably the first thing you have heard of (/going to hear). Service workers (by those, who have heard of them, at least), are mostly known for being a replacement for AppCache, and bringing offline support for web applications. Some developers tend to respond to this by "we already have AppCache and it works all right", but truth is, several quirks and footguns await for those who dare to try to enhance their app with offline support by using AppCache. The declarative manifest file might also seem easier to handle, but the lack of flexibility that stems from this declarative nature makes it pretty hard to accomplish more complicated offline functionality.
> Service workers come in at this point, providing a lot of key basic principles (some of them just being specced, either as part of the specification (Cache API), or outside of it (Fetch, URL, Storage API)). These key princibles/building blocks and their well-defined interactions make it possible for web developers to expand on the platform-provided functionalities to their own liking, accomplishing their own needs.

---

# Diving into
## Offline support with service workers

* Adding offline support & best practices
* Hands on

---

---

# Performance boost
* Great control over caching mechanism
* On-demand & pre-caching of resources
* Intuitive cache busting
* Protections against being "stuck"

> Even if your webapp doesn't need offline functionality (it's based around a service, so it needs to be online to be useful - a bit more on this later), you might still benefit from having a service worker. Just as you'd benefit from a properly set-up AppCache manifest, or even properly set up caching headers, you could use service workers to enhance your application's performance, user experience.
> Caching assets, precaching predictable pages/paths, offlining data and providing local "autocomplete" results and cached older feed entries until networked API requests complete are all improving the real and *percieved* performance of your application, both being incredibly important from your prospective user's viewpoint.
> Through smart caching, moving computation to the client side, prediction and other methods it is not only your user's experience you are improving on -- but you are saving network bandwith, server load and on the long run improving user experience (due to improved responsiveness of the less burdened server ecosystem) by spending less.

---

---

# Background Sync

---

# What does it even mean?
#### ...to be offline?

* What does it mean to be "offline"?
* Lie-fi
* Offline-first

---

---

> What does offline mean? Operator's network being down due to hailstorm? Hiking at Mount Etna? Flying above the Antarctica in a wingsuit? Well offline could be caused by anything. Large metallic structures, overloaded networks, underground, bad reception... What's even worse is being "barely online". Crappy internet - as said by Matthew Inman of The Oatmeal - is *way-way-way* worse than no internet. You are *seemingly* online, but your phone can not send. Your e-mail ends up unsent, your tweet garbled, your photo half-uploaded. Apps mostly handle these situations, but webapps just tend to beachball endlessly in a never-ending throbber you can not even cancel, unless realoading the page, which then, of course will get rid of all the formdata you painstakingly just typed.
> *ARGH*. Yes, it's frustrating - that's exactly why you should make your (web)apps offline first? Writing a tweet? Save it! Save it often. Send it when there is (good) connection. Posting an image? Save it. Did it fail to upload? Try it again later a few times, maybe it was just an intermittent interruption in the network.

---

# Background Sync API

* Experimental API
* Gives you an "inbox/outbox"
* Lets you sync your data
* Scheduled syncs
* Server/user initiated syncs

> The Background Sync API lets you do all those above which are implemented in (better) proprietary apps: it provides you with the primitives to easily store data until it could be delivered, also serves as an inbox for your incoming data. Data inbox/outboxes are synchronized on select intervals automatically, request from the user or to a server-sent event (generally, a Push message). All the primitives are created to make sure no data loss could occur.

---

# Diving into
## Background sync
* Background sync in practice

---

---

# Push Notifications

* Responding to server-sent events
* Can be used with
    * Notification API
    * Background Sync API

> Network information transfer is hard. You could keep a connection open, and poll a server, but that's going to have adverse effects on your battery life and dataplan. Push Notifications help you receive timely events from your server, "pings", that new information is at your service. You could then respond by showing pop-up notifications, or starting a new data sync, keeping your webapp (and its user) up to date.

---

# Diving into
## Push notifications
* Push notifications in practice

---

---

# Whatever you make of them

* Polyfilling future web features?
* API emulation & proxying?
* Render caching & performance upgrade?
* Geofencing?

> Whether it is polyfilling future web platform features (see the workshop on creating your on service worker!), emulating remote APIs, optimizing application load, rendering and localization like Firefox OS does or Geofencing (which is a new experimental spec, based on service workers) -- service workers are just laying the groundwork. They are scriptable proxies, a "bedrock API", exposing the "magic" behind your daily browsing (network fetches, caching...). A primitive you could use to "roll your own" solution. Of course, "with great power comes great responsibility" - spec authors and browser implementors try very make sure nothing could go wrong, and the API could not be abused, but you should take care and use these powerful tools responsibly.

---

---

### A word on
# Progressive enhancement

* You can use this, now
* But you shouldn't rely on it
    * Might not be available
    * Could break anytime
* Use Progressive Enhancement
    * Feature detect!
    * Add SW as an enhancement
    * for users who already have it
    * do not rely on it

> Service workers are a new and experimental technology. But it's already shipping in some browsers (Chrome has some of the API since early 2015 shipping in stable). That also means the feature is unavailable for a lot of the users who are going to use your webapp or website. You should provide fallbacks for these users -- even so, you should **build** for these users, and provide SW-based functionalities to users who could take it, so nobody is left behind or staring to a white blank window.
> Make sure you do feature detection, and not browser sniffing to decide who to provide the enhanced experience with, so new browsers joining in the future could *automagically* have the new experience from day one of their release!
> Service workers are also unstable. That means, even if you use them, be prepared that sometime they could break, or change in ways you haven't accepted. Breaking could not really be circumvented, young volatile APIs tend to be a bit on the brittle side of the spectrum. Be prepared. Also, follow the specification, as it could change in ways that require you to modify the application. These breaking changes are rare, but certainly not non-existent.
