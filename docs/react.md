# REACT

<br>---<br>

## REACT FC
<br>---<br>

<h4>React FC</h4>

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