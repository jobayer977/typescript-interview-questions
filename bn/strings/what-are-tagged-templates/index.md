---
title:  ট্যাগ করা টেমপ্লেট কি?
---
## ট্যাগ করা টেমপ্লেট কি?

ট্যাগ করা টেমপ্লেট হল টেমপ্লেটের উন্নত রূপ। এটি একটি ফাংশন এ  টেমপ্লেট পার্স করার অনুমতি দেয়। ফাংশনটি প্রথম প্যারামিটারটিকে স্ট্রিংয়ের অ্যারে হিসাবে গ্রহণ করে  এবং বাকি প্যারামিটারগুলিকে এক্সপ্রেশন এর মান  গ্রহণ করে।
**Example**

```javascript
    var user1 = "John";
    var skill1 = "JavaScript";
    var experience1 = 15;

    var user2 = "Kane";
    var skill2 = "JavaScript";
    var experience2 = 5;

    function myInfoTag(strings, userExp, experienceExp, skillExp) {
    var str0 = strings[0]; // "Mr/Ms. "
    var str1 = strings[1]; // " is a/an "
    var str2 = strings[2]; // "in"

    var expertiseStr;
    if (experienceExp > 10) {
        expertiseStr = "expert developer";
    } else if (skillExp > 5 && skillExp <= 10) {
        expertiseStr = "senior developer";
    } else {
        expertiseStr = "junior developer";
    }

    return `${str0}${userExp}${str1}${expertiseStr}${str2}${skillExp}`;
    }

    var output1 = myInfoTag`Mr/Ms. ${user1} is a/an ${experience1} in ${skill1}`;
    var output2 = myInfoTag`Mr/Ms. ${user2} is a/an ${experience2} in ${skill2}`;

    console.log(output1); // Mr/Ms. John is a/an expert developer in JavaScript
    console.log(output2); // Mr/Ms. Kane is a/an junior developer in JavaScript
```
