---
title:  Raw স্ট্রিং কি?
---
## Raw স্ট্রিং কি?

এটি সিকোয়েন্সগুলি এড়ানোর জন্য প্রক্রিয়াকরণ ছাড়াই টেমপ্লেট লিটারালগুলির Raw স্ট্রিং ফর্ম পেতে ব্যবহৃত হয়|

```javascript
var str = `Hello world \n Jon Snow`;
console.log(str);
// Hello world
//  Jon Snow

var rawStr = String.raw`Hello world \n Jon Snow`;
console.log(rawStr); //Hello world \n Jon Snow

```
