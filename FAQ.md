# Service Worker FAQ

## Is the service worker spec final?

No, currently the specification (as of June 2015) is [still in the working draft state](http://www.w3.org/TR/2015/WD-service-workers-20150625/)
— you may want to follow the discussion on [GitHub](https://github.com/slightlyoff/ServiceWorker/issues/),
or get the latest spec-related highlights on [Twitter](https://twitter.com/service_workers).

##  What browsers support service workers?

Visit [isServiceWorkerReady](https://jakearchibald.github.io/isserviceworkerready/)
by Jake Archibald to track the service worker implementation status.

## Can I use service workers in production?

It depends on your use case and your target platform. Service worker support [shipped
in Chrome 40 stable](https://www.chromium.org/blink/serviceworker) so you certainly
could use them in production, if you wanted.

## Should I use service workers in production?

If you are familiar with the notion of [progressive enhancement](https://en.wikipedia.org/wiki/Progressive_enhancement)
— service workers are a perfect candidate for progressively-enhancing your website/webapp.

You should use feature detection, to check for service worker support and add offline
capabilities, or notifications support for those browsers that already implement
the spec.
