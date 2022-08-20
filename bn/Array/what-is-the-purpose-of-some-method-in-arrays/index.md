---
title:  Array some ফাঙ্কশন কেন ব্যবহার করা হয় ?
---
## Array some ফাঙ্কশন কেন ব্যবহার করা হয় ?

Array  `some`  মেথড ব্যবহার করা হয়।  টেস্ট কেস  সর্বনিম্ন একটা এলিমেন্ট পাশ করে কিনা চেক করার জন্য।

```javascript
var array = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

var odd = (element) => element % 2 !== 0;

console.log(array.some(odd)); // true (the odd element exists)
```
