# Tuple

跟 C# 用法差不多

- 宣告方式

```tsx
let student: [number, string];

student = [1, "Kappa"];
```

```tsx
let student: [number, string] = [1, "Kappa"];

// 取值
console.log(student); // [ 1, 'Kappa' ]
console.log(student[0]); // 1
console.log(student[1]); // "Kappa"
```

- 新增東西用 `push`，但型別會被受限於 tuple 宣告的 union 裡面
- 不過我還不太懂 push 實際的用法在哪 XD

```tsx
let student: [number, string] = [1, "Kappa"];

// 只能是 number or string
student.push("test");
student.push(87);

console.log(student); // [ 1, 'Kappa', 'test', 87 ]
```
