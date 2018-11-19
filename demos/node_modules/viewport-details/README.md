# Viewport details
Get cached viewport details

## Install
You can install via npm or yarn

### npm
```bash
npm install --save viewport-details
```

### yarn
```bash
yarn add viewport-details
```

## Usage

### Importing
You can import using ES6 imports
```javascript
import { GetViewportDetails } from 'viewport-deails';
```
### Getting details
```javascript
console.log(GetViewportDetails());
```
Will return:
```typescript
interface IViewportDetails {
  width: number;
  height: number;
  heightCollapsedControls: number;
  scrollX: number;
	scrollY: number;
	orientation: string | number;
  resized: boolean;
	scrolled: boolean;
	orientationChanged: boolean;
  scrollDirectionX: number;
	scrollDirectionY: number;
	previous: IViewportDetails;
	changed: boolean;
}
```

#### Note:
_**heightCollapsedControls**_ is the height that the viewport will be once the user has scrolled and the browser controlls shrink, such as on iOS Safari.

_**resized**_ represents whether the viewport resized since the previous animation frame.

_**scrolled**_ represents whether the viewport scrolled since the previous animation frame.

_**scrollDirectionX**_ represents a the direction of scroll. 0 means no movement, 1 means scrolling to the right, and -1 means scrolling to the left. 

If you're using TypeScript an enum (EScrollDirectionX) is also available, with the options None, Right, and Left.

_**scrollDirectionY**_ represents a the direction of scroll. 0 means no movement, 1 means scrolling down, and -1 means scrolling up.

If you're using TypeScript an enum (EScrollDirectionY) is also available, with the options None, Up, and Down.
