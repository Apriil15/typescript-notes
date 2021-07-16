# Type 型別

TS 中型別有兩種：`primitive type`、`object type`

其中 primitive type (原始型別) 有：boolean、number、string、null、undefined 和 ES6 的 Symbol

- 宣告方式

```tsx
let a: boolean = false;
let b: number = 98;
let c: string = "test";
let d: string = `${c}123`; // 嵌入變數
let e: undefined = undefined;
let f: null = null;

console.log(a);
console.log(b);
console.log(c);
console.log(d);
console.log(e);
console.log(f);
```

- 不回傳用 `void`

```tsx
function test(num: number): void {
  console.log(num);
}

test(87);
```
