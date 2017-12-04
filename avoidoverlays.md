Avoid areas provide an easy way to ensure the subject of an image is positioned in free space, not behind text or another overlay. See a quick example below:

@[jsfiddle](q6wu82ru)

The *salieo-avoid* class (or a custom class as specified with [avoid_class](#avoid_class)) can be applied to any object that is positioned over an image that Salieo will process. Salieo will then automatically position the subject of the image in the largest rectangle of free space either to the right, left, top or bottom of that object.

Try editing the fiddle and removing the *salieo-avoid* class from the text to see the difference.

To override which side of the avoid area the subject is positioned, refer to the full documentation on [Avoid Area options](https://github.com/salieo/salieo.js#avoid-areas).
