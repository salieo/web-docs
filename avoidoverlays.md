Avoid areas provide an easy way to ensure the subject of an image is positioned in free space, not behind text or another overlay. See a quick example below:

@[jsfiddle](tv7ndhvg)

The `salieo-avoid` class (or a custom class as specified with [`avoid_class`](#avoid_class)) can be applied to any object that is positioned over an image that salieo will process. Salieo will then automatically set the [`focus`](https://github.com/salieo/cropcalc-js#focus-1) for that image to be the largest rectangle of free space either to the right, left, top or bottom of that object. The [`zoom`](https://github.com/salieo/cropcalc-js#zoom) option for that image will also be set to [`"focus"`](https://github.com/salieo/cropcalc-js#focus).

**NOTE:** [Crop Options](#crop-options) specified on an image *always* take precedence and will override any settings set by the avoid area calculation. For example, you could set `data-salieo-zoom` to `false` on an image while still using an avoid area to simply shift the image into the appropirate position without any zooming. Global [`crop_options`](#crop_options) set in the options passed when initializing salieo.js will, however, be overridden by the options set through the avoid area calculation.

### Avoid Area Options

The behaviour of an avoid area can optionally be controlled by applying the `data-salieo-avoid` attribute to the element with the [avoid_class](#avoid_class).

**NOTE:** The `data-salieo-avoid` attribute should be applied to the element to be avoided, *not* the image.

**Example:**

This example sets any images that fall below this text element to center the subject in the free space to the right of the text element.

```
<p class="salieo-avoid" data-salieo-avoid="right">Avoid this!</p>
```

#### auto

This is the default setting. The area of free space to the left, right, top and bottom of the element to be avoided will be calculated. The free space region with the largest area will be selected and the subject of the image being positioned will be centered within it.

If the area of the largest region is *not* at least 20% larger than its opposite region (i.e. the left region is opposite the right region, and the top opposite the bottom, etc.) the avoid area will be ignored and the focus area will be the entire width and height of the image element. For example, this is especially helpful for responsive designs where an element to be avoided may be positioned near the left for larger screen sizes (resulting in the right region being selected for the focus area) but center positioned for smaller screen sizes resulting in the avoid area being ignored and the subject being centered behind the text.

For more control, the behaviour of the avoid area region selection can be selected manually with one of the options below.

#### left

The region to the left of the element to be avoided will always be selected as the focus area.

#### right

The region to the right of the element to be avoided will always be selected as the focus area.

#### top

The region above the element to be avoided will always be selected as the focus area.

#### bottom

The region below the element to be avoided will always be selected as the focus area.