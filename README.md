# React Native Photo Browser

A full screen photo browser with captions, selections and grid view support for react-native. Layout and API design are inspired by great [MWPhotoBrowser](https://github.com/mwaterfall/MWPhotoBrowser) library.

It has iOS only support currently but android support will be implemented very soon.

![](screenshots/photo-browser.gif)

![](screenshots/screenshot-1.png)
![](screenshots/screenshot-2.png)

### Installation 
1. npm install react-native-photo-browser --save

### Properties

| Prop | Type | Description | Default |
|---|---|---|---|
|**`mediaList`**|Array\<Media\>|List of [media objects](#media-object) to display.|`[]`|
|**`initialIndex`**|Number|Sets the visible photo initially.|`0`|
|**`alwaysShowControls`**|Boolean|Allows to control whether the bars and controls are always visible or whether they fade away to show the photo full.|`false`|
|**`displayActionButton`**|Boolean|Show action button to allow sharing, copying, etc.|`true`|
|**`displayNavArrows`**|Boolean|Whether to display left and right nav arrows on bottom toolbar.|`false`|
|**`enableGrid`**|Boolean|Whether to allow the viewing of all the photo thumbnails on a grid.|`true`|
|**`startOnGrid`**|Boolean|Whether to start on the grid of thumbnails instead of the first photo.|`false`|
|**`displaySelectionButtons`**|Boolean|Whether selection buttons are shown on each image.|`false`|
|**`useCircleProgress`**|Boolean|Displays Progress.Circle instead of default Progress.Bar for full screen photos. Check [Progress](#progress-component) section for more info.|`false`|
|**`onSelectionChanged`**|Function|Called when a media item is selected or unselected.|`(media, index, isSelected) => {}`|
|**`onActionButton`**|Function|Called when action button is pressed for a photo. If you don't provide this props, ActionSheetIOS will be opened by default.|`(media, index) => {}`|
|**`onBack`**|Function|Called when back button is tapped.|`() => {}`|

### Media Object

```js
const media = {
  thumb: '', // thumbnail version of the photo to be displayed in grid view. actual photo is used if thumb is not provided
  photo: '', // a remote photo or local media url
  caption: '', // photo caption to be displayed
  selected: true, // set the photo selected initially(default is false)
};
```


### Progress Component

[react-native-progress](https://github.com/oblador/react-native-progress) component is used as progress indicator. The default progress component is `Progress.Bar`. You can also use `Progress.Circle` component by simply using `useCircleProgress` prop, and adding `ReactART` library to your Xcode project. For more information please check out [react-native-progress repo](https://github.com/oblador/react-native-progress#reactart-based-components) and [React Native documentation](http://facebook.github.io/react-native/docs/linking-libraries-ios.html#content).


### Examples

See [index.ios.js](Example/index.ios.js) file.

Follow those steps to run the example:

1.  Clone the repo `git clone https://github.com/halilb/react-native-photo-browser && cd react-native-photo-browser`
2.  Install dependencies `npm install``
3. Open `PhotoBrowserExample.xcodeproj` file in Xcode and run


### Known issues
* The component doesn't perform well with big photo lists.
* Sharing a remote photo is basically sharing it's screenshot currently, and this breaks the photo resolution. Converting the image to base64 is a solution but ImageStore didn't provide efficient API performance-wise.

### Roadmap
* [ ] Improve performance for bigger collections
* [ ] Android support
* [ ] Photo zoom
* [ ] Video support
* [ ] Zooming photos to fill the screen

### Licence
[MIT](http://opensource.org/licenses/mit-license.html)
