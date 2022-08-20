---
title: কিভাবে  dynamically CSS এবং JS ফাইল লোড করা  যায় ?
---
## কিভাবে  dynamically CSS এবং JS ফাইল লোড করা  যায় ?

Dynamically  DOM-এ লিঙ্ক এবং স্ক্রিপ্ট উভয় এলিমেন্ট  তৈরি করে তা  হেড ট্যাগে চাইল্ড  হিসেবে এপেন্ড করলে dynamically লোড করা যাবে |

```javascript
function loadAssets(filename, filetype) {
  if (filetype == "css") {
    // External CSS file
    var fileReference = document.createElement("link");
    fileReference.setAttribute("rel", "stylesheet");
    fileReference.setAttribute("type", "text/css");
    fileReference.setAttribute("href", filename);
  } else if (filetype == "js") {
    // External JavaScript file
    var fileReference = document.createElement("script");
    fileReference.setAttribute("type", "text/javascript");
    fileReference.setAttribute("src", filename);
  }
  if (typeof fileReference != "undefined")
    document.getElementsByTagName("head")[0].appendChild(fileReference);
}
```
