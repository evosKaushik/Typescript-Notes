# 📝 Understanding Promise<T> in TypeScript

## Promise constructor

```ts
// 1st way
const myPromise = new Promise<string>((resolve, reject)=>{
  resolve("Hi")
})

// 2st way
const myPromise: Promise<string> = new Promise((resolve, reject)=>{
  resolve("Hi")
})
```

When we solve this we got string