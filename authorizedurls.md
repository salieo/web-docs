You can control what images can be processed on your account by specifying authorized url patterns (glob patterns). This way you can prevent others from using your image quota to process their images. The `*` character matches any number of any characters and the `?` character matches any single character.

The order of the rules makes no difference, as long as an incomming request to process an image matches at least one rule it will be processed, otherwise the request will fail.

For example, setting `*example.com/img/*` as a rule would allow all images containing *example.com/img/* to be processed.

Setting `*example.com/img/pic_?.jpg` would allow the following (note the character that `?` matches doesn't have to be a number): *http://www.example.com/img/pic_1.jpg*, *http://www.example.com/img/pic_2.jpg* etc.

You can also specify rules for individual images with no wildcards to individually allow a single image. For example the rule `http://www.example.com/image.jpg` would only match that one specific image.