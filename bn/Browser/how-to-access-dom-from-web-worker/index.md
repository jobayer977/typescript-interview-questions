---
title:  ওয়েব ওয়ার্কার থেকে কিভাবে DOM এ এক্সেস করা যায় ?
---
## ওয়েব ওয়ার্কার থেকে কিভাবে DOM এ এক্সেস করা যায় ?

ওয়েব ওয়ার্কার এর ব্রাউসার  এর ডোম এক্সেস করা যায় না, কারন এক্সেকিউশন  থ্রেড সেফ রাখার জন্য। তবে পোস্টমেসেজে  এর মাধ্যমে  ব্রাউসার উইন্ডো আর সাথে কমিউনিকেশন স্থপন করেতে পারে। তাই postmessage এর উপর ভিত্তি করে ডোম আপডেট করা যায়।

**Example**

```html
<html>
 <body>
  <h1 id="time">Time:</h1>
 </body>
 <script>
  const time = document.getElementById('time');
  const worker = new Worker('worker.js');
  worker.onmessage = (e) => {
   time.innerHTML = e.data;
  };
 </script>
</html>

```

`worker.js`

```javascript
setInterval(() => {
 postMessage(new Date().toLocaleString());
}, 1000);
```

**Output**

```nginx
8/9/2022, 1:08:24 AM  
```
