# progress-bar
* * *
## - images
![](http://i.imgur.com/5SO5YP9.gif)
* * *
## - installation

1. Download the repository
2. Import both and `libs/x-tag-core.min.js` and `templates/progress-bars.js`.

```html
<script src="[path-to-progress-bars]/libs/x-tag-core.min.js"></script>
<script src="[path-to-progress-bars]/templates/progress-bars.js"></script>
```
* * *
## - use
Just insert one of the progress bar tags and set its attributes. 

Example:
`<circular-progress-bar-status progressStringFormat="{p}%"></circular-progress-bar-status>`
* * *
## - bars, attributes and functions:
Each bar contains its own attributes and functions. Some bars are inherited from each other, those who are inherited will have all the its own attributes and functions plus the parent ones.

### prototype-progress-bar (abstract)
:warning: **_warning:_**: _This bar should not be used. All other bars will inherit from this one._

##### attributes
* isundeterminated: <br/>
	* Returns zero (0) if the bar is set as defined and one (1) if the bar is set as undefined
	* :warning: **_warning:_**: _This is **read-only**! To set a bar as undefined take a look at `setUndefined` in the **functions section**._
* barcolor: <br/>
	* Gets or sets the color of the bar
	* :warning: **_warning:_**: _This should be a hex color containing all seven digits (example: "#FF0000")._
* filledcolor: <br/>
	* Gets or sets the color of the bar when it is filled
* progress: <br/>
	* Gets or sets the progress of the bar
* donetext: <br/>
	* Gets or sets the text that should (or should not? see next attribute) be displayed when the progress is set to 100% (_a.k.a the job is done_)
* displaytextwhendone: <br/>
	* Gets or sets a value indicating if the `donetext` should replace the progress of the bar when it's set to 100%
* progressstringformat: <br/>
	* Gets or sets a string informing how the progress should be displayed. It must contain the following string to be replaced as the progress: `{p}`.
	* Example: `Progress: <b>{p}</b>%` will produce: "Progress: **100**%"

### circular-progress-bar : prototype-progress-bar
##### attributes
* circlesize: <br/>
	* Gets or sets the width and height of the circle
* barsize: <br/>
	* Gets or sets the size (thickness?) of the bar
* circlebackground: <br/>
	* Gets or sets the hexadecimal color for the circle backgorund
	
##### functions
* setUndeterminated(isUndeterminated)
    * Sets the bar as defined or undefined
    * **param: isUndeterminated**
        * Zero if the bar should be defined, one if it should be undefined

### circular-progress-bar-status : circular-progress-bar
##### attributes
* status: <br/>
	* Gets or sets the status that should be displayed under the bar
	* :heavy_exclamation_mark: This can contain HTML markup (such as `<img>` or `<b>`)
* * *

## - to-do: 
- [x] Add circular bars
- [X] Create a decent `README.md`
- [ ] Add more bars
