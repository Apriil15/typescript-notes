# Generics 泛型

跟 C# 差不多，定義方法時不指定型別，使用時再決定

- 一般寫法

```tsx
function theSame<T>(something: T): T {
  return something;
}

// 可以指定預設型別
function theSame2<T = string>(something: T): T {
  return something;
}

let result: number = theSame(123);
let result2: string = theSame("test");

console.log(result); // 123
console.log(result2); // test
```

- 多個參數

```tsx
function swap<T, U>(tuple: [T, U]): [U, T] {
  return [tuple[1], tuple[0]];
}

let result = swap([7, "seven"]);
console.log(result); // [ 'seven', 7 ]
```

- 泛型約束：`<T extends something>`

```tsx
interface Teacher extends Faculty {
  subject: string;
}

interface Student extends Faculty {
  score: number;
}

// 教職員
interface Faculty {
  id: number;
}

// 限定要傳入教職員
function theSame<T extends Faculty>(someone: T): T {
  console.log(someone.id); // 只有 id 這個共同屬性能調用
  return someone;
}

let student: Student = { id: 1, score: 87 };
console.log(theSame(student));
```

- 泛型類別

```tsx
class Something<T> {
  public value: T;
  public constructor(value: T) {
    this.value = value;
  }
}

let something: Something<number> = new Something<number>(123);
console.log(something.value);

let something2: Something<string> = new Something<string>("Kappa");
console.log(something2.value);
```
