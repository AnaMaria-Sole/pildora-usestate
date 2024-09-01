
# React ´useState´ Hook Examples


This repository contains simple examples demonstrating the use of the ´useState´ hook in React. The useState hook is a fundamental feature in React that allows you to add state to functional components.


## Table of Contents
- Introduction
- Getting Started
- Examples
  - Contador
  - ActualizarTexto
  - Nombre
- Running the Examples
# Introduction

The useState hook is used to manage the state in a React functional component. It returns an array containing the current state value and a function to update that value. This hook allows you to add local state to your components, which can be modified over time in response to user interactions or other events.
## Getting Started

Before you start, make sure you have Node.js and npm installed on your machine.

1. Clone the repository:

```bash
  git clone https://github.com/AnaMaria-Sole/pildora-usestate.git
cd pildora-usestate

```
2. Install the dependencies:

```bash
npm install

```
3. Start the development server:

```bash
npm start
```
## Examples

### Contador

```javascript
import React, { useState } from 'react';
import './App.css';

function Contador() {
  const [counter, setCounter] = useState(0);

  return (
    <div className="App">
      <h1>{counter}</h1>
      <button onClick={() => setCounter(counter + 2)}>
        INCREMENTAR
      </button>
      <button onClick={() => setCounter(counter - 1)}>
        DECREMENTAR
      </button>
    </div>
  );
}

export default Contador;

```

### ActualizarTexto
The `ActualizarTexto` component shows how to update state with text input from the user. As the user types in the input field, the displayed text updates in real-time.

```javascript
import React, { useState } from 'react';
import './App.css';

function ActualizarTexto() {
  const [text, setText] = useState('');

  return (
    <div className="App">
      <input
        type="text"
        value={text}
        onChange={(e) => setText(e.target.value)}
      />
      <p>Texto actual: {text}</p>
    </div>
  );
}

export default ActualizarTexto;
````

### Nombre
The `Nombre` component demonstrates how to manage more complex state objects. It allows the user to change the name displayed on the screen by clicking a button.
```javascript
import React, { useState } from 'react';
import './App.css';

function Nombre() {
  const [person, setPerson] = useState({
    name: "Ana Victoria",
  });

  function handleNameChange() {
    setPerson({
      ...person,
      name: "Ophelia",
    });
  }

  return (
    <div className="App">
      <h1>{person.name}</h1>
      <button onClick={handleNameChange}>
        CAMBIAR
      </button>
    </div>
  );
}

export default Nombre;
````
## Running the Examples
To run any of the examples, replace the component imported in App.js with the one you want to test. For example, to test the Contador component:
1. Open `src/App.js` and modify the import statement:
```javascript
import Contador from './Contador';
````
2. Ensure that App.js renders the Contador component:
```javascript
function App() {
  return (
    <div className="App">
      <Contador />
    </div>
  );
}

export default App;
````
3. Save the file, and the development server should automatically reload, showing the `Contador` component in action.
Repeat the above steps for `ActualizarTexto` and `Nombre` to test those components.
    
## Conclusion
These examples should give you a basic understanding of how to use the `useState` hook to manage state in functional React components. Feel free to experiment with the code and expand on these examples to learn more about state management in React.