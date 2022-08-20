---
title: for...of কি?
---
## What is for...of statement

জাভাস্ক্রিপ্ট for of  লুপ করে  এইটারবল ডাটাস্ট্রাটারে মাঝে এবং ভ্যালু এক্সট্র্যাক্ট করে।  এটি কাজ করে  **Arrays, Strings, Maps, NodeLists,**

```javascript
const cars = ["BMW", "Volvo", "Mini"];

let text = "";
for (let x of cars) {
  text += x;
}

// BMW
// Volvo
// Mini
```
