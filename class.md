# Class 類別

基本上跟 C# 大同小異

- 有三種 Access Modifiers 可以用：`public`、`private`、`protected`

  protected: 類似 private，但在`子類別裡面可以被調用`

- 繼承用關鍵字 `extends`
- `readonly`: 不能再被修改

---

- 基本寫法

```tsx
class Animal {
  public readonly name: string;
  constructor(name: string) {
    this.name = name;
  }

  public SayHi() {
    console.log(`${this.name} say hi`);
  }
}

let animal = new Animal("test");
console.log(animal);

// readonly 不能被修改，會報錯
animal.name = "test2";
```

- static: 靜態屬性、方法

  不需要 instance，可以直接用 class 名稱呼叫

```tsx
class Animal {
  public name: string;
  public static order = 1;

  constructor(name: string) {
    this.name = name;
  }

  static SayHi() {
    console.log("Hi!");
  }
}

Animal.SayHi();
console.log(Animal.order);
```

- Abstract Class

```tsx
abstract class Animal {
  // 子類別才可調用
  protected name: string;

  constructor(name: string) {
    this.name = name;
  }

  public abstract sayHi(): void;
}

class Dog extends Animal {
  constructor(name: string) {
    super(name);
  }

  // need to implement
  public sayHi(): void {
    console.log(`${this.name} say hi!`);
  }
}

let dog: Dog = new Dog("Doggy");
dog.sayHi();
```

- Parameter Properties（精簡的寫法）

  把修飾詞寫在建構子裡面

```tsx
class Student {
  constructor(public name: string, public age: number) {}
}

const student = new Student("Sam", 27);

console.log(student.name);
```

等同此寫法

```tsx
class Student {
  name: string;
  age: number;
  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }
}
```
