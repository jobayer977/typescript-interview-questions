---
title:  কিভাবে destructuring assignments এ ডিফল্ট ভ্যালু সেট করা যায় ?
---
## কিভাবে destructuring assignments এ ডিফল্ট ভ্যালু সেট করা যায় ?

যখন destructuring করা হয় তখন ভ্যারিয়েবল এর  প্রাথমিক মানটি অনির্ধারিত থাকে। আমরা destructuring ভ্যারিয়েবল এর  প্রাথমিক মান নির্ধারণ করতে পারি destructuring assignments এর মাধমে ।

**Arrays destructuring:**

```javascript
var x, y, z;

[x = 2, y = 4, z = 6] = [10];
console.log(x); // 10
console.log(y); // 4
console.log(z); // 6
```

**Objects destructuring:**

```javascript
var { x = 2, y = 4, z = 6 } = { x: 10 };

console.log(x); // 10
console.log(y); // 4
console.log(z); // 6
```
