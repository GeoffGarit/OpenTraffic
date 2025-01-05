# OpenTraffic

OpenTraffic is an open-source alternative to WTraffic under licence MIT.

## How to use OpenTraffic ?

OpenTraffic is a simple HTML/CSS/JS project, you just have to make your own `traffic/train.json` file using OTJson file formatting (explain below) and open `index.html` on any browser. Alternatively, `open-traffic.js` can be implemented on any other webpage given it has the necessary context.

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

| name        | String - Name of the train. Not in use currently. (Optional)                                                         |
|-------------|----------------------------------------------------------------------------------------------------------------------|
| direction   | Enum - Direction of the train. Can be 'L', 'R', 'any' or empty. (Optional)                                           |
| speed       | Integer - Maximum speed of the train in km/h.                                                                        |
| composition | Array - array of images URL of your train elements. Can also contain a repeatting order in the form "\<quantity>*'\<image_url>'". |
| background  | String - Background image URL. If not used, the default image provided is used. (Optional)                           |
| foregroung  | String - Foreground image URL. If not used, no foreground image shows. (Optional)                                    |

