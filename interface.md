# Interface

宣告變數時，形狀要跟 interface 一致，多一個少一個都不行

### 可選屬性

- 屬性後面加上 `?`，可寫可不寫

### 任意屬性

- 寫法：`[anyName: string]: any`

  前半段：自定義的名稱為 string

  後半段：值為 any type

- 如果使用了任意屬性，則該 interface 其它屬性的型別都要是 any 的子集

### 唯讀屬性

- 屬性前加上 `readonly`，宣告變數時一定要 assign，之後不能再 assign

### 範例

```tsx
interface Person {
  readonly Name: string;
  Age?: number;

  // 如果把 any 改成 string，"Age?: number" 就會報錯，因為 number 不是 string 的子集
  [anyName: string]: any;
}

let person: Person = {
  Name: "Tom", // readonly -> 宣告時一定要 assign
  Age: 27, // 可寫可不寫
  Gender: "male",
};

person.Name = "Kevin"; // Name 是 readonly 不能再 assign，會報錯
```
