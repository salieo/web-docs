You can get started with Salieo by including the [salieo.js](https://github.com/salieo/salieo.js) library in your site's `<head>` with the following:

```
<script src="https://cdn.jsdelivr.net/npm/salieo.js@0/dist/salieo.min.js" defer></script>
```

Or if you'd rather use your own build system that's fine too. As salieo.js is built as a UMD bundle, you can use it with just about any module loader you like.

```
npm install salieo.js
```

[salieo.js](https://github.com/salieo/salieo.js) can work on any element with a CSS `background-image` or any `<img>` element. Just add the `salieo` class (or the custom class you specified with the [img_class](#img_class) option) and watch the images pop into place.

## Setup

Create an instance, passing in your [options](#options).

```
var instance;
document.addEventListener("DOMContentLoaded", function() {
    instance = new salieo({
        site_id: "YOURSITEID"
    });
});
```

**NOTE:** If an salieo instance isn't initialized early enough during page load, your images may not be positioned properly before they are displayed resulting in a noticeable jump when they reposition. To avoid this, ensure the following:

1. As mentioned previously, if you are using a `<script>` tag to load salieo.js you should include it in your `<head>` *not* at the end of `<body>` as one may be used to. As long as the script is loaded with the `defer` tag it won't block rendering while loading and will ensure salieo.js is fully loaded before the `DOMContentLoaded` event fires.
2. A salieo instance should be created when the the `DOMContentLoaded` event fires. Creating the instance before the DOM has fully loaded could result in salieo not finding all images that need processing. Conversly, creating the instance after the `DOMContentLoaded` event, (i.e. on the `load` event) will likely not give salieo enough time to reposition the images before they are displayed.

## How does it work?

salieo.js uses [cropcalc-js](https://github.com/salieo/cropcalc-js) to calculate the best crop for an image based on data returned from the Salieo API. 

salieo.js requests crop direction information from the Salieo API for all enabled images on your site. If the Salieo API has not processed this image before it may take a second to do so (resulting in a small delay between the time your images load and when they are repositioned and/or scaled by salieo.js). Don't worry though, this only happens once.

After the images are processed the first time by the Salieo API, the results are cached on a global CDN to enable near instantaneous delivery of the data for future page loads anywhere in the world. This way, subsequent page loads should not see any visible jump when salieo.js repositions the images. The data is loaded and the transformations are applied all before the image loads.
