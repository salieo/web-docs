### Salieo API v1.0.0

The Salieo API provides direct access to the crop direction data that powers [salieo.js](https://github.com/salieo/salieo.js) and can be used for a variety of applications.

@[apiendpoint](GET,https://api.salieo.com/v1/crop)

### Example

```
GET https://api.salieo.com/v1/crop?url=https://www.salieo.com/testimg/test1.jpg&key=myapikey
```

```
{
	"crops": {
		"suggested": [{
			"x2": 1998,
			"y2": 1444,
			"y1": 552,
			"x1": 0,
			"id": 1
		}, {
			"x2": 1998,
			"y2": 1444,
			"y1": 646,
			"x1": 962,
			"id": 2
		}],
		"fallback": [{
			"x2": 1694,
			"y2": 955,
			"y1": 679,
			"x1": 1427,
			"id": 1
		}],
	},
	"orig_width": 2000,
	"orig_height": 1446
}
```

### Query Parameters

**url** - The URL of the image to process and generate crop direction data for.

**key** - API Authentication Key

### Response

**orig_width** - Width of the processed image in px.

**orig_height** - Height of the processed image in px.

**crops.suggested** - List of the suggested crops for the image (could be empty).

**crops.fallback** - List of the fallback crops for the image (could be empty).