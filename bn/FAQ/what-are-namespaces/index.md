---
title:  Namespaces কি ?
---
## Namespaces কি ?

namespace  একটি প্রোগ্রামিং দৃষ্টান্ত যা  ভ্যারিয়েবল এর  নামকরণের সংঘর্ষ এড়াতে ব্যবহৃত হয়। লজিকাল কোড  গ্রুপিং  করতে সাহায্য করুন। JavaScript ডিফল্টরূপে namespace প্রদান করে না। যাইহোক, আমরা একটি গ্লোবাল অবজেক্ট তৈরি করে namespace ব্যবহার করতে পারি যাতে সমস্ত ফাংশন এবং ভেরিয়েবল থাকতে পারে।

**Example**

```javascript
const service = {
 get: function () {
  // Get Api Implemented
 },
 put: function () {
  // put Api Implemented
 },
 post: function () {
  // post Api Implmented
 }
};

service.get();
service.post();
```
