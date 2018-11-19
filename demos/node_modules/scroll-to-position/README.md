# scroll-to-position
Animate scroll to either an x, y, or x and y position in any scrollable viewport with customisable easing.

## Install
You can install via npm or yarn.

### npm
```bash
npm install --save scroll-to-position
```

### yarn
```bash
yarn add scroll-to-position
```

## Usage

### Importing
You can import using ES6 imports.
```javascript
import { ScrollTo } from 'scroll-to-position';
```

### Arguments
ScrollTo accepts two arguments:

**target**: either a position ([positionX, positionY]) or a HTML Element (e.g. a refrence to a div).

**options** _(optional)_: an object of configuration options - see the options section below.

#### Examples

**Position**
```javascript
ScrollTo([0, 100]);
```

**Element**
```javascript
const myElement = document.querySelector('.MyElement');
ScrollTo(myElement);
```

_Note: if you're using TypeScript you will most likely need to cast your element to a HTMLElement, as document.querySelector returns a Element type._


## Options

When calling ScrollTo you can provide an options object, with values to override the defaults.

### Option Parameters

| Parameter | Type | Description | Default |
|-----------|------|-------------|---------|
| scrollContainer | HTMLElement or Window | The area to scroll. e.g. window or a div with overflow auto | window |
| offset | Position ([number, number]) | If your target is a HTMLElement you may want to provide an offset to prevent scrolling right to the edge of the element | [0,0] |
| duration | DurationRange ([number, number]) or Duration (number) | Either a DurationRange ([minDuration, maxDuration]) or a set duration (all values in milliseconds). If you provide a range the scroll distance (providing it's no less than the minDuration and no more than the maxDuration will be used as the duration) | [200, 5000] |
| easing | string | The easing function the animation will use. The easing's available can be seein in my js-easing-functions repo (https://github.com/bameyrick/js-easing-functions) | https://github.com/bameyrick/js-easing-functions |
| cancelOnUserScroll | boolean | Whether the scroll animation should stop when the user scrolls | true | 
| animate | boolean | Whether ScrollTo should animate to the target, or jump straight there with no animation | true |
| autoDurationMultiplier | number | If duration is to picked automatically (between DurationRange), multiply the distance to travel by this value to get the duration | 2 |

### Example of providing options
```javascript
ScrollTo([0, 100], {
  duration: [300, 1000],
  easing: 'easeInOutSine',
});
```

## Extras
An `autoScroll` boolean is added to the window which you can use in your scroll event listeners to check if the window is being autoScrolled buy this package.
