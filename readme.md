#A Simple Vue HTML Container With A Fixed Aspect Ratio

Use this container when you want a div with a fixed aspect ratio, defined by you, like: 1/1 or 16/9... or any other ratio.

The width of the container will be 100% of the parent container. The container will set its height, so that it will always have the given aspect ratio.
Include in the container any HTML that you want.

##Install

``$ npm install apl-vue-ar-container``

or

``$ yarn add apl-vue-ar-container``

##Usage

**In a Vue file:**

```javascript
import ArContainer from 'apl-vue-ar-container';

export default {
	components: {
        'ar-container': ArContainer,
	},

    //...
}
```

**In a js file (like Laravel's app.js):**

```javascript
window.Vue = require('vue');

Vue.component('ar-container', require('apl-vue-ar-container').default);

const app = new Vue({
    el: '#app',
});
```

**Then in your HTML:**

```html
<ar-container ar="4/3">
    <div style="position:absolute;top:0;bottom:0;right:0;left:0;background:url('/path/to/an/image.jpg');background-size:cover;"></div>
</ar-container>
```

###Parameters

* **ar** - (mandatory) The aspect ratio of the container, as a string with the format: WIDTH/HEIGHT (e.g. 1/1, 16/9, 4/3 etc.)

###Styling

The container has `position: relative`, so you can insert an absolutely positioned element and stretch it to the limits of the container.

For example, you can insert an image you want to display with a fixed aspect ratio.

You can assign any classes to the container. The container and its inner HTML elements only have the minimum inline styling to fulfill their purpose.