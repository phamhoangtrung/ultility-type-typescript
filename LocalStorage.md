```ts
interface Storage {
  getObjectItem: <T extends string>(key: T) => LocalStorageValue<T> | null;
}

type LocalStorageKey = keyof LocalStorage;
type LocalStorageValue<T> = T extends LocalStorageKey ? LocalStorage[T] : unknown;

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

// const token: `Beaer ${string}` | null
const token = localStorage.getObjectItem('token');

// const address: {
//    phoneNumber:number
// } | null
const address = localStorage.getObjectItem('address');

// const listItem: {
//    id:string,
//    name:string
// }[] | null
const listItem = localStorage.getObjectItem('items');

```
