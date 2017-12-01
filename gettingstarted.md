First, make sure you've setup your site on your Salieo account. If you haven't done this yet you will want to do so before proceeding.

### Include Script

Next, you can get started with Salieo by including the [salieo.js](https://github.com/salieo/salieo.js) library in your site's `<head>` with the following:

```
<script src="https://cdn.jsdelivr.net/npm/salieo.js@0/dist/salieo.min.js" defer></script>
```

You can find comprehensive documentation of all the [salieo.js](https://github.com/salieo/salieo.js) features and options [here](https://github.com/salieo/salieo.js).

### Create Instance

Create an instance, passing in your [options](#https://github.com/salieo/salieo.js#options).

```
var instance;
document.addEventListener("DOMContentLoaded", function() {
    instance = new salieo({
        site_id: "YOURSITEID"
    });
});
```