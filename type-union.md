# Union 型別

- 宣告方式用 `|` 來分隔型別

```tsx
// 可以是 string or number 型別
let a: string | number;

a = "test";
console.log(a);

a = 87;
console.log(a);
```

- 用在 function，只能使用`共同的方法、屬性`

  `toString()` 是 number、string 共同的方法，所以可以使用；如果改成 `length` 會報錯

```tsx
function getString(something: number | string): string {
  return something.toString();
}

console.log(getString(98));
console.log(getString("test"));
```

- union type 的變數被 assign 時，會根據型別推論的規則推斷出當下型別

```tsx
let something: string | number;

// 目前是 string
something = "test";
console.log(something.length);

// 目前是 number
something = 98;
console.log(something.length); // 會報錯
```
