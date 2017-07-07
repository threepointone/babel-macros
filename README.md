babel-macros
---

UPDATE - work on this will likely happen over at [Kent's repo](https://github.com/kentcdodds/babel-macros) 

(this is a readme for a project that I want to exist. previous work - [sweetjs](http://sweetjs.org/), [babel-plugin-macros](https://github.com/codemix/babel-plugin-macros))

a macro is a function that takes source code as input, and modifies it. 

input
```jsx
// hello.macros.js 
export default function hello(x){
  // do whatever with the node  
  x.replaceWithSourceString(`console.log('hello' + ${x.toSource()})`))
}

// app.js
import hello from './hello.macros'

hello('sunil')
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


usage 
---
add `'babel-macros'` to your babel config's `plugins` field. 
