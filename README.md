# OpenTraffic

OpenTraffic is an open-source alternative to WTraffic, released under the MIT license.

## How to use OpenTraffic ?

OpenTraffic is a simple HTML/CSS/JS project. To use it, you need to create a `traffic/train.json` file using the OTJson format (explained below) and open `index.html` in any browser. Alternatively, you can integrate `open-traffic.js` into another webpage, provided the necessary context is set up.

### Local usage restriction

Due to CORS policies implemented in modern browsers, OpenTraffic will not work if opened via the `file://` protocol. You must use an HTTP server to access it through the `http://` or `https://` protocol.

### What is OTJson ?

OTJson is the json formatting used by OpenTraffic. Here's an example :
```json
[
	{
		"name": "Train Name",
		"direction": "any",
		"speed": 160,
		"composition": [
			"https://example.com/locomotive.png",
			"2*'https://example.com/A.png'",
			"5*'https://example.com/B.png'"
		],
		"background": "./assets/bg-default.png",
		"foreground": "./assets/cat-midi.png"
	}
]
```
---
It's an array of "trains" where each objects is a different train. The train is defined by :

| Attribute     | Description                                                                                     | Type     | Example                                        |
|---------------|-------------------------------------------------------------------------------------------------|----------|------------------------------------------------|
| **name**      | The name of the train. Not currently used.                                                      | `string` | `"Train Name"`                                 |
| **direction** | The train's direction. Can be `'L'` (left-to-right), `'R'` (right-to-left), `'any'`, or empty.  | `string` | `"R"`                                          |
| **speed**     | The train's maximum speed in km/h. (Required)                                                   | `number` | `160`                                          |
| **composition**| Array of image URLs for the train's elements. Supports repeating patterns in the format `<quantity>*'<image_url>'`. (Required) | `array`  | `["2*'https://example.com/A.png'"]`           |
| **background**| The URL of the background image. If not provided, a default image will be used.                 | `string` | `"./assets/bg-default.png"`                   |
| **foreground**| The URL of the foreground image. If not provided, no foreground will be displayed.              | `string` | `"./assets/cat-midi.png"`                     |
