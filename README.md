# utilities-type-typescript

```ts
interface Storage {
  getObjectItem: <T extends string>(key: T) => LocalStorageValue<T>;
}

type LocalStorageKey = keyof LocalStorage;
type LocalStorageValue<T> = T extends LocalStorageKey ? LocalStorage[T] : any;

interface LocalStorage {
  user: {
    name: string;
    age: number;
  };
  token: `Bearer ${string}`;
  items: {
    id: string;
    name: string;
  }[];
}

interface LocalStorage {
  address: {
    phoneNumber: number;
  };
}
```

```ts
localStorage.getObjectItem = function (key) {
  const jsonItem = this.getItem(key);
  return jsonItem && JSON.parse(jsonItem);
};

// const token: `Beaer ${string}`
const token = localStorage.getObjectItem('token');

// const address: {
//    phoneNumber:number
// }
const address = localStorage.getObjectItem('address');

// const listItem: {
//    id:string,
//    name:string
// }[]
const listItem = localStorage.getObjectItem('items');

```
