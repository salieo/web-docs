First, make sure you've setup your site on your Salieo account. If you haven't done this yet you will want to do so before proceeding.

### Include salieo.js
Next, you can get started with Salieo by including the [salieo.js](https://github.com/salieo/salieo.js) library in your site's `<head>` with the following:

```html
<script src="https://cdn.jsdelivr.net/npm/salieo.js@0/dist/salieo.min.js" defer></script>
```

You can find comprehensive documentation of all the [salieo.js](https://github.com/salieo/salieo.js) features and options [here](https://github.com/salieo/salieo.js).

### Create Instance

Create an instance, passing in your [options](https://github.com/salieo/salieo.js#options).

```javascript
var instance;
document.addEventListener("DOMContentLoaded", function() {
    instance = new salieo({
        site_id: "YOURSITEID"
    });
});
```

**NOTE:** It's important that [salieo.js](https://github.com/salieo/salieo.js)  is included in your site's `<head>` **and** is initialized right after the `DOMContentLoaded` event to ensure there is enough time to load the crop direction data and apply the transformations to your images *before* they are displayed (resulting in no visible jump when the images reposition). More information about initializing [salieo.js](https://github.com/salieo/salieo.js) can be found [here](https://github.com/salieo/salieo.js#getting-started).

### Setup an image

To activate Salieo on your first image, add the *salieo* class to any `<img>` element or element with a CSS `background-image`. You can also specify a custom class to use (instead of the default *salieo*) with the [img_class](https://github.com/salieo/salieo.js#img_class) option.

@[jsfiddle](x0od69rw)

To fine tune how your image is positioned or scaled there are a variety of crop options that can be set [globally](https://github.com/salieo/salieo.js#crop_options) (for all images) or [per-image](https://github.com/salieo/salieo.js#crop-options). Here's the same image with the **zoom** set to *auto*.

@[jsfiddle](1o2runm3)
