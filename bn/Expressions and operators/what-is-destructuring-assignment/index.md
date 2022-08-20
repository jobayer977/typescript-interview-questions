---
title:  ডিস্ট্রাকচারিং অ্যাসাইনমেন্ট কি?
---
## ডিস্ট্রাকচারিং অ্যাসাইনমেন্ট কি?

ডিস্ট্রাকচারিং অ্যাসাইনমেন্ট হল জাভাস্ক্রিপ্ট এক্সপ্রেশন যা অ্যারে থেকে মানগুলি বা অবজেক্ট  থেকে প্রপার্টি কে আলাদা ভ্যারিয়েবল এ রেফারেন্স করতে সাহায্য  করে।

```javascript
var [one, two, three] = ["JAN", "FEB", "MARCH"];

console.log(one); // "JAN"
console.log(two); // "FEB"
console.log(three); // "MARCH"
```

```javascript
var { name, age } = { name: "John", age: 32 };

console.log(name); // John
console.log(age); // 32
```
