# ultility-type-typescript
```ts
interface LocalStorage {
  user: {
    name:string,
    age:number
  };
  token:`Beaer ${string}`;
  cookie:number;
}

type LocalStorageKey = keyof LocalStorage
type LocalStorageValue<T> = T extends LocalStorageKey ? LocalStorage[T]: any;


interface LocalStorage {
  address:{
    phoneNumber:number
  }
}


function getStorage<T extends string>(key:T):LocalStorageValue<T>{
  return key as any
}
const a = getStorage("address")
```
