# String Literal 字串字面量

- 用來限制只能是定義的字串

```tsx
type Language = "TS" | "Golang";

function print(choice: Language): void {
  if (choice == "Golang") {
    console.log(choice);
    return;
  } else if (choice == "TS") {
    console.log(choice);
    return;
  }
  throw new Error();
}

print("Golang");
```
