# REACT

<br>

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