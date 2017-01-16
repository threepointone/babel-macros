babel-macros
---

(this is a readme for a project that I want to exist. previous work - [sweetjs](http://sweetjs.org/), [babel-plugin-macros](https://github.com/codemix/babel-plugin-macros))

a macro is a function that takes source code as input, and modifies it. 

input - 
```jsx
import defmacro from 'babel-macros'

let log = defmacro(x => 
  x.replaceWithSourceString(`console.log('hello' + ${x.toSource()})`))

log('sunil')
```

output
```jsx
console.log('hello' + 'sunil')
```

Works across common function call types 
```jsx
x(...)
<X .../>
x`...`
```

should be able to export / import across modules 
```jsx
// x.js 
export const x = defmacro(...)

// app.js 
import { x } from './x.js'
x(...)
```

usage 
---
add `'babel-macros'` to your babel config's `plugins` field. 
