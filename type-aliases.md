# Type Aliases 型別別名

- 常用於 `union type`

```tsx
type NumberOrString = number | string;

function getLength(something: NumberOrString): number {
  if (typeof something === "number") {
    return something.toString().length;
  } else if (typeof something === "string") {
    return something.length;
  }
  throw new Error();
}

console.log(getLength(123));
console.log(getLength("456"));
```
