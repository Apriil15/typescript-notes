# Enum 列舉

- 沒手動給值，會是預設

```tsx
enum Days {
  Sun, // 0
  Mon, // 1
  Tue, // 2
  Wed, // 以此類推
  Thu,
  Fri,
  Sat,
}

console.log(Days["Sun"]); // 0
console.log(Days[0]); // Sun
```

- 手動給值（要注意不要重複）

```tsx
enum Days {
  Sun = 7,
  Mon = 1,
  Tue, // 2
  Wed, // 3
  Thu, // 以此類推
  Fri,
  Sat,
}

console.log(Days["Sun"]); // 0
console.log(Days[2]); // Tue
```
