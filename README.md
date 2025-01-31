# Hackjam : Intro to React

Adapted from HackJam Whack a mole in Reason (https://github.com/IwanKaramazow/ReasonDojoAlicante) by @IwanKaramazow

## Install

```
git clone [repo-link]
```

### With npm

```
npm install
npm start
```

### With yarn

```
yarn
yarn start
```

## End goal

Take a look : https://sad-liskov-0b5a7f.netlify.com/

## Hello World

Modify the rendered text in `App.js` into "Hello React !"

## Create your first component

Integrate this custom button in `App.js` :

```js
<Button text='Start game!' />
```
Note that this is not html but JSX: https://reactjs.org/docs/introducing-jsx.html
This simplifies a dev's job and it is optional: https://reactjs.org/docs/react-without-jsx.html

Now create the custom button component `Button.js`.

1. It's a React Component that will render a `<button>` with a custom inner text
2. To render the custom text in `App.js` use a **prop**: https://reactjs.org/docs/components-and-props.html

## Create a static version of the board

The board will contain 9 grounds. The goal is to render the content of our board multiple times :

```js
<div className='board'>
  <div className='board-item'>
    <div className='mole'> </div>
    <div className='ground'> </div>
  </div>
</div>
```

Create a component `Board.js` for this.

## Create a dynamic version of your board

Repeating code is not optimal, following this concept you can turn your static board into a dynamic one: https://reactjs.org/docs/lists-and-keys.html

_Hint_ You can only **map** over an **array**

## State

States are a way for your App to store values and keep their content after re-renders.
Each value is stored in a state object :

```js
state = {
    first: "value",
    second: 123,
    third: fourth: {fifth: 432},
    ...
}
```

More info for **reading** and **setting** a state value: https://reactjs.org/docs/state-and-lifecycle.html

Now, using states, show the score in `App.js` and increment it on every click of the Button component created previously.

_Hint_ Here the click event on `<Button>` will be a **prop** and won't be handled like a `<button>` in CSS.

## Moles... Moles everywhere...

1. Create a function that will make a mole appear randomly. (Use the commented **changeActiveMole** function in `App.js`)
   _Hint_ Create a state to store the random number (the mole appearing)
2. Use `setTimeout()` to create an interval during which the mole will appear
   _Hint_ To make the mole appear from the ground, take a look at `/src/static/style.css`

## Whack that mole !

Now that you have moles popping up from everywhere every second you should implement the commented **hit** function !

You should divide your game into different states :

- Waiting (before clicking the start button)
- Start of the game (default state)
- Hitting a mole (incrementing the score)
- Play (moles are appearing randomly)

## So you're finished and bored ?

- Take a look to this new React feature and rewrite the app to use it: https://reactjs.org/docs/hooks-intro.html
- Replace style.css by styled components: https://www.styled-components.com/docs/basics
- You can spam an appearing mole and increment the score quickly: fix this so that each time a mole appear can only hit it once.
- Create a pause button
- Create a stop button and save your score on a score table.
- Have fun !
