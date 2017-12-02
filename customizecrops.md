If you aren't quite pleased with how Salieo is positioning your image you can easily override the crop data for an image.

Simply log into your Salieo account and navigate to your site's dashboard. You'll see a section called **Manage Images**. If you know the URL of the image you want to edit the crops for you can enter it in the search field. You can also choose **Select On Site** to select the image from your site.

By editing the crops, you can change how [salieo.js](https://github.com/salieo/salieo.js) will position/scale the image on your site. Note that you may have to clear your browser's cache to see new changes on your site after you edit the crops for an image.

Salieo uses two types of crops, *suggested* and *fallback*. For more detailed information on how these types of crops affect the image's position and scale on your site, refer to the [cropcalc-js docs](https://github.com/salieo/cropcalc-js#zoom) (cropcalc-js is the library used by salieo.js to calculate the best crop for the images on your site).

### Suggested Crops

Suggested Crops (highlited in green) define crops that contain all the most critical parts of an image. The smallest suggested crop should contain only the most critical components of an image. Salieo will always attempt to maintain all of the smallest suggested crop in view. If no suggested crops are provided, the entire image is taken as a suggested crop and salieo will attempt to always maintain as much of it as possible when positioning/scaling that image on your site.

### Fallback Crops

Fallback Crops (highlighted in red) define crops that should only be used when the smallest suggested crop cannot be contained. A suggested crop could contain a person while a fallback crop would contain just the face. Multiple fallback crops can be specified, each within the other (all crops can only have a maximum of one direct child crop). Salieo will attempt to contain the largest fallback crop possible when positioning/scaling an iamge.

