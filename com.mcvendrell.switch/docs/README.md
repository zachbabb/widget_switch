# Switch Widget Sample

The **Switch** widget provides an styled switch for Android/mobileweb with the holo style. Also works on iOS, but the native iOS is better, of course.

![Animation example](img/switch.gif)

(this is not the real speed, this GIF is a lot more slow)

**NOTE**: My first version, that works with an ScrollView, is in the *scrollView* branch. But the master version is better in terms of accuracy (just touch any part of the switch and changes automatically). Old is like this:
![Old Animation example](img/switchOld.gif)

##Manifest
* Version: 1.1 (stable)
* Github: https://github.com/mcvendrell/widget_switch
* License: [Apache 2.0](http://www.apache.org/licenses/LICENSE-2.0.html)
* Author: Manuel Conde
* Supported Platforms: Android, Mobileweb

## Adding the Switch Widget to Your Alloy Project

* In your application's config.json file you will want to include the following line in your dependencies:

```
"dependencies": {
    "com.mcvendrell.switch": "1.1"
}
```

*  Create a widgets directory in your app directory if it doesn't already exist.
*  Copy the com.mcvendrell.switch folder into your app/widgets directory. 

## Create a Switch in the View
You can add a Switch to a view by *requiring* the switch widget. 

	<Widget id="mySwitch" src="com.mcvendrell.switch"/>

Assign it an ID that you can use in your controller. E.g. `id="mySwitch"` You can now access the Switch via `$.mySwitch` in your controller.

```
Ti.API.info("switch value " + $.mySwitch.value);
```

## Detect a Switch change
You can detect a Switch change simply adding a onChange event. 

	<Widget id="mySwitch" src="com.mcvendrell.switch" onChange="myChangeFunction" />

You can now access the Switch change in your controller:

```
function myChangeFunction(e){
    Ti.API.info("Change detected. Value: " + e.value);
}
```

## Position and Style the Switch
In your .tss file for the view, you can style and position your Switch as you would any other control, using any valid properties for [Ti.UI.View object](http://docs.appcelerator.com/titanium/latest/#!/api/Titanium.UI.View).

```
"#mySwitch": {
    top: 5, 
    width: 65, 
}
```

## Initializing the Switch in the Controller

The Switch is off by default. Before you open your window, you need to call the Switch with the *init* method. For example:

```
$.mySwitch.init($.getView());
```
### Initialization Parameters

| Parameter | Type | Description |
| --------- | ---- | ----------- |
| args | *object* | An object containing the arguments for initialization. |
| args.parentView | *Ti.UI.View* | Top level view to display the picker in. |
| [args.*parameters*] | *various* | Any valid [Ti.UI.View](http://docs.appcelerator.com/titanium/latest/#!/api/Titanium.UI.View) key/value pairs that you want applied to the Switch appearance. It is recommended that you set these in the parent tss file where possible. |

## Accessible Properties and Methods
| Properties | Type | Description |
| ---------- | ---- | ----------- |
| value | *boolean* | *Read/Write.* A boolean value to set/get the switch state: true = ON; false = OFF. |

## Localization
In order to support localization and avoid translation problems, I have chosen to use icons instead of text, so, in the doc/img folder you have 2 options to overwrite the default assets images folders. Choose what you prefer:

![My choice](img/off.png) - ![](img/on.png)

![Option 2](img/off_plain.png) - ![](img/on_plain.png)

Or you can edit it and make your own.
