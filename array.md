# Array 陣列

寫法：

1. type + [ ]
2. Array<type>
3. any[ ]

```tsx
// type + []
let arr1: number[] = [1, 2, 3];
arr1.push(4, 5);
console.log(arr1);

// 泛型寫法
let arr2: Array<number> = [1, 2, 3];
console.log(arr2);

// 用 any 表示允許任意型別
let arr3: any[] = [1, "test", true, { name: "Kappa" }];
console.log(arr3);
```
