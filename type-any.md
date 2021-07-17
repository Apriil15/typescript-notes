# Any 型別

- any 可以被 assign 任意型別

```tsx
// any 可以被 assign 任意型別
let a: any = "test";
console.log(a);

a = 87;
console.log(a);

a = true;
console.log(a);
```

- 宣告時不指定型別，就會是 any

```tsx
// 等同於 let something: any;
let something;

something = true;
console.log(something);

something = 98;
console.log(something);
```
