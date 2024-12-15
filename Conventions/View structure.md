# View structure

Grouping code parts for View, Fragment, Activity and ViewController classes depending on the OS to organize variables, methods and business logic.

## Basics

Each grouping should be labeled in the code with an appropriate comment indicating the name of the group and subgroup, if necessary.

```
// ****************
// Group – subgroup
```

Each group is separated by 2 empty lines, and within a group each method or variable is separated by 1 empty line.


## Groups

### Callbacks

Lambda methods which are called to notify parent View, Fragment, Activity or ViewController and pass data or states to it if necessary.

Name of methods should contain keywords like `clicked`, `tapped`, `switched`, `changed`, `selected` etc.


### Extras

**Private** variables which are populated from the data that was passed via Intents to newly created Activity from another Fragment or Activity in Android.


### Properties

Set of supporting **private** variables, including data models and view models, which are used throughout the lifecycle of screen or component.

Variables should be grouped under different comments, indicating the name of the subgroup.

```
// Properties – data, loading, status etc
```


### Views

Set of **private** views which are displayed permanently or temporarily on the screen or in a component, used and edited exclusively within the object in which they were created by calling available modification methods.

Name of views should contain keywords like `View`, `LinearLayout`, `StackView`, `Button` to point to the parent, whether it is a default UI element or a custom-built one component.

If both permanent and temporary views are displayed on the screen, they should be separated into different subgroups.

```
// ****************
// Views – permanent, temporary
```


### Setup

Set of **private** supporting methods for initializing the screen in general, extra and local variables and views that are always displayed on the screen or shown temporary.

The order of initialization methods always remains unchanged, accompanied by relevant comments.

```
// ****************
// Setup – screen, extras, properties, views
```


### Listeners

Set of **private** methods to track changes in screen display, offsets or theme, and user interaction with views.

The methods are called when screen or component is initialized.

Name of methods should be structure with leading `listenFor` keyword, following with the name of view and resulting with the action like `Click`, `Switch` or property which is observed like `Offset`, `Theme` etc.


### Modifications

Set of **private** and **public** methods for changing the content in displayed views and their appearance with passing corresponding parameters if needed.

Name of methods should start with keyword `set`, following with the name of property like `Title`, `Color`, `Icon` or display state like `Selected`, `Active` etc.


### Presentation

**Private** methods for controlling the display of temporary views on the screen such as loading, alert message and others which can be either shown or hidden.

Name of the methods should begin with the keywords `show` and `hide` following with the name of the view.


### Navigation

**Private** methods which allow to navigate from the current screen to another screen, open a page in a browser, or open another application.

Name of methods should begin with keywords `show` or `open` following with the name of the view or external application with context.


### Requesting

**Private** methods which are called exclusively to make an API request to retrieve, send, or modify data.

They can be called either at the beginning of a screen or component display, or as a result of some user action.

As a result of the request, methods from the `Presentation` or `Modifications` groups should be used to modify the screen display and its contents.

Name of methods should begin with keywords `receive`, `send` and `edit` following with the name of data.


### Lifecycle

Standard **override** methods for monitoring screen or component display status when it appears, hides, etc., and to get data from other screens if needed.
