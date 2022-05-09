```ts
// Array have infinity lenght while tupple have fixed
// Infinity + 1 = Infinity
// 6 + 1 = 7

type IsTuple<T> = T extends readonly any[] 
  ? [...T,any]['length'] extends T['length']
    ? false // this is Infinity case
    : true
  :false
```
