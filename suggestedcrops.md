![Example of Suggested and Fallback Crops](https://raw.githubusercontent.com/salieo/web-docs/master/img/example_crops.PNG)

Suggested Crops (highlighted in green) define crops that contain all the most critical parts of an image. The smallest suggested crop should contain only the most critical components of an image.

[cropcalc-js](https://github.com/salieo/cropcalc-js) will always attempt to maintain all of the smallest suggested crop in view. If no suggested crops are provided, the entire image is taken as a suggested crop.