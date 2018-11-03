# Reactivity
Reactivity is a simple component that makes tracking user activity easy and lets you decide how to act upon a users active state.

## 💾 Installation
*It is recommended to use [yarn](https://yarnpkg.com/)*.
```sh
yarn add @toles/reactivity
```
or
```sh
npm install --save @toles/reactivity
```
## ⏳ Usage

Add the component right next to the element it will be tracking activity on.  In this case, we're tracking user activity for the application in general so we add it at the root and attach it to the window.

```javascript
ReactDOM.render(
    <>
        <Idle
            onActive={() => console.log('active')}
            onIdle={() => console.log('idle')}
            gracePeriod={10000/*ms*/}
            element={window} />
        <App />
    </>,
    document.getElementById('root')
);
```

## 📃Documentation
### Default Events
* click
* mousedown
* mousemove
* mouseover
* mouseup
* keypress
* keyup
* touchstart
* touchend
* touchmove
* touchcancel
* scroll
* resize

### Props
* **element** *{[EventTarget](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget)}* - The target being tracked.
* **gracePeriod** *{number}* - The amount of time allowed before being considered idle. (ms)
* **onIdle** *{function}* - Function to call on idle.
* **onActive** *{function}* - Function to call on active.