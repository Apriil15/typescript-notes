# 相關 Command

- 安裝 typescript、ts-node

  ```powershell
  # 安裝
  npm install -g typescript ts-node
  ```

- 確認版本

  ```bash
  $ tsc -v
  Version 4.3.5
  ```

- 產生 tsconfig.json

  ```powershell
  tsc --init
  ```

- 編譯 TypeScript 檔案

  ```powershell
  # compile all files
  tsc

  # compile specific file
  tsc index.ts
  ```

- 執行 ts-node

  ```powershell
  ts-node index.ts
  ```
