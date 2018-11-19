# Tick Manager
Utility to add functions to queues to tick using requestAnimationFrame

## Install
You can install via npm or yarn

### npm
```bash
npm install --save tick-manager
```

### yarn
```bash
yarn add tick-manager
```

## Usage
There are 3 available queues to add tick functions too: Initial Ticks, Pre Ticks, and Ticks. The manager will run all this ticks in Initial Ticks first, followed by Pre Ticks, and then finally Ticks. This can be useful if you need to guarantee that one function runs before another that uses data from the first, but you can't guarantee what order AddTick will be called in each of those functions.

### Importing
You can import the any of the three functions into your project using ES6 imports
```javascript
import { AddInitialTick, AddPreTick, AddTick } from 'tick-manager';
```
### Adding a tick to an array
You can add a function to an array as follows _(Note: The tick manager will begin running this function at the next animation frame and every one thereafter)_.
```javascript
function myAmazingTickFunction() {
    // do stuff
}

AddTick(myAmazingTickFunction);
```
