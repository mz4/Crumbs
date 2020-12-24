# REACT

<br>

---

<br>

# Hooks

we often can’t break complex components down any further because the logic is stateful and can’t be extracted to a function or another component.
Hooks let us organize the logic inside a component into reusable isolated units.

Hooks apply the React philosophy (explicit data flow and composition) inside a component, rather than just between the components. That’s why I feel that Hooks are a natural fit for the React component model.

Components are more powerful, but they have to render some UI. This makes them inconvenient for sharing non-visual logic. This is how we end up with complex patterns like render props and higher-order components. Wouldn’t React be simpler if there was just one common way to reuse code instead of so many?


Functions seem to be a perfect mechanism for code reuse. Moving logic between functions takes the least amount of effort. However, functions can’t have local React state inside them. You can’t extract behavior like “watch window size and update the state” or “animate a value over time”.

<br>

---

<br>

# useState

```js
import React, { useState } from 'react';

const clickComponent = () => {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Clicked {count} times.</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  )
}
```

<br>

---

<br>

# useEffect

```js
import React, { useState, useEffect } from 'react';
import { fetchEmployees } from './fetchEmployees';

const Employees = ({ query }) => {
  const [employees, setEmployees] = useState([]);

  useEffect(() => {
    const fetch = async () => {
      setEmployees(await fetchEmployees(query))
    }
    fetch()
  }, [query]);

  return (
    <div>
      {employees.map(name => <div>{name}</div>)}
    </div>
  )
}
```

<br>

---

<br>

# UseContext

```js

const themes = {
  light: {
    foreground: '#000',
    background: '#eee'
  },
  dark: {
    foreground: '#eee',
    background: '#000'
  }
}

const ThemeContext = React.createContext(themes.light);

function App() {
  return (
    <ThemeContext.Provider value={themes.dark}>
      <Toolbar />
    </ThemeContext>
  )
}

function Toolbar(props) {
  return (
    <div>
      <ThemedButton />
    </div>
  )
}

function ThemeButton() {
  const theme = useContext(ThemeContext);

  return (
    <button style={{ background: theme.background, color:theme.foregroudn }}>
      Click me
    </button>
  )
}
```

<br>

---

<br>

# UseContext Demo


<iframe src="https://codesandbox.io/embed/updating-shared-react-context-from-child-components-with-hooks-forked-fucsb?fontsize=14&hidenavigation=1&theme=dark" style="width:100%; height:500px; border:0; border-radius: 4px; overflow:hidden;" title="Updating Shared React Context from Child Components with Hooks (forked)" allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking" sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"></iframe>

<br>

---

<br>

# useReducer Demo

<iframe src="https://codesandbox.io/embed/usereducer-todo-app-forked-43qk4?fontsize=14&hidenavigation=1&theme=dark" style="width:100%; height:500px; border:0; border-radius: 4px; overflow:hidden;" title="useReducer todo app (forked)" allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking" sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"></iframe>

<br>

---

<br>

# useCallback Demo

<iframe src="https://codesandbox.io/embed/reactusecallback-forked-d1401?fontsize=14&hidenavigation=1&theme=dark" style="width:100%; height:500px; border:0; border-radius: 4px; overflow:hidden;" title="React.useCallback (forked)" allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking" sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"></iframe>

<br>

---

<br>

# React Memo Demo

<p>React memo is used to wrap React components to prevent re-renderings</p>

<iframe src="https://codesandbox.io/embed/thirsty-hellman-mytul?fontsize=14&hidenavigation=1&theme=dark" style="width:100%; height:500px; border:0; border-radius: 4px; overflow:hidden;" title="thirsty-hellman-mytul" allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking" sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"></iframe>

<br>

---

<br>

# Custom Hook - useWindowSize

<iframe src="https://codesandbox.io/embed/exciting-ellis-zzic6?fontsize=14&hidenavigation=1&theme=dark" style="width:100%; height:500px; border:0; border-radius: 4px; overflow:hidden;" title="exciting-ellis-zzic6" allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking" sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"></iframe>

<br>

---

</br>

# Custom Hook - useTimeout

<iframe src="https://codesandbox.io/embed/magical-hawking-ijcvq?fontsize=14&hidenavigation=1&theme=dark" style="width:100%; height:500px; border:0; border-radius: 4px; overflow:hidden;" title="magical-hawking-ijcvq" allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking" sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"></iframe>

<br>

---

</br>
