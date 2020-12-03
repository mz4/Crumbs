# REACT

<br>

## Hooks

<h4>Stateless function component - sfc</h4>

```js
const | = props => {
  return ( | );
};

export default |;
```

<h4>React FC - useState</h4>

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

<h4>React FC - useEffect</h4>

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

<h4>React FC - UseContext</h4>

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

<h4>React FC - Update UseContext</h4>


<iframe src="https://codesandbox.io/embed/updating-shared-react-context-from-child-components-with-hooks-forked-fucsb?fontsize=14&hidenavigation=1&theme=dark" style="width:100%; height:500px; border:0; border-radius: 4px; overflow:hidden;" title="Updating Shared React Context from Child Components with Hooks (forked)" allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking" sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"></iframe>


<br>

<h4>React FC - useReducer</h4>

<iframe src="https://codesandbox.io/embed/usereducer-todo-app-forked-43qk4?fontsize=14&hidenavigation=1&theme=dark" style="width:100%; height:500px; border:0; border-radius: 4px; overflow:hidden;" title="useReducer todo app (forked)" allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking" sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"></iframe>

<br>

<h4>React FC - useCallback</h4>

<iframe src="https://codesandbox.io/embed/reactusecallback-forked-d1401?fontsize=14&hidenavigation=1&theme=dark" style="width:100%; height:500px; border:0; border-radius: 4px; overflow:hidden;" title="React.useCallback (forked)" allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking" sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"></iframe>