# Function 函式

- Function Declaration 函式宣告

  JS

  ```jsx
  function sum(x, y) {
    return x + y;
  }
  ```

  改寫成 TS

  ```tsx
  function sum(x: number, y: number): number {
    return x + y;
  }
  ```

- Function Expression 函式表示式

  JS

  ```jsx
  var mySum = function (x, y) {
    return x + y;
  };
  ```

  改寫成 TS

  ```tsx
  // 只有對右邊匿名 function 定義型別
  // 左邊 sum2 的型別是 assign 時，才型別推論出來的
  let sum2 = function (x: number, y: number): number {
    return x + y;
  };

  // TS 中的 "=>" 表示函式的定義，左邊是輸入型別，右邊是輸出型別
  let sum3: (x: number, y: number) => number = function (
    x: number,
    y: number
  ): number {
    return x + y;
  };
  ```

- 用 interface 來定義 function

  ```tsx
  interface Sum {
    (x: number, y: number): number;
  }

  let test: Sum = function (x: number, y: number): number {
    return x + y;
  };

  console.log(test(1, 2));
  ```

- 可選參數

  - 參數後面加上 `?`
  - 可選參數一定要放在必要參數的後面

  ```tsx
  // z 為可選參數
  function sum(x: number, y: number, z?: number): number {
    if (z) {
      return x + y + z;
    }
    return x + y;
  }

  console.log(sum(1, 2));
  console.log(sum(1, 2, 3));
  ```

- 參數預設值

  - 寫法類似 C#

  ```tsx
  // z 預設為 3
  function sum(x: number, y: number, z: number = 3): number {
    return x + y + z;
  }

  console.log(sum(1, 2));
  console.log(sum(1, 2, 4));
  ```

- 剩餘參數

  - 類似 Golang 的 `variadic function`

  ```tsx
  function sum(...numbers: number[]): number {
    let result: number = 0;

    numbers.forEach((number) => {
      result += number;
    });

    return result;
  }

  let result: number = sum(1, 2, 3);
  console.log(result);
  ```

- Overload

  ```tsx
  // 定義
  function sum(x: number, y: number): number;
  function sum(x: string, y: string): string;

  // 實現
  function sum(x: number | string, y: number | string): number | string {
    if (typeof x === "number" && typeof y === "number") {
      return x + y;
    } else if (typeof x === "string" && typeof y === "string") {
      return x + y;
    }
    throw new Error();
  }

  // 可以明確地知道目前是用哪個 function
  console.log(sum(1, 2));
  console.log(sum("a", "b"));
  ```
