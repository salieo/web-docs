![Example of Suggested and Fallback Crops](https://raw.githubusercontent.com/salieo/web-docs/master/img/example_crops.PNG)

Fallback Crops (highlighted in red) define crops that should only be used when the smallest suggested crop cannot be contained. A suggested crop could contain a person while a fallback crop would contain just the face. Multiple fallback crops can be specified, each within the other (all crops can only have a maximum of one direct child crop).

[cropcalc-js](https://github.com/salieo/cropcalc-js) will attempt to contain the largest fallback crop possible when generating a custom crop.