# Interview Question of the Week Solutions
Solutions for the 'interview question of the week' section from Cassidy Williams' weekly newsletter. You can subscribe [here](https://cassidoo.co/newsletter/). Done in JavaScript. 
## 4/02/20 Issue
Given that an "even word" is a word in which each character appears an even number of times, write a function that takes in a string and returns the minimum number of letters to be removed to make that string an even word.

Example:
```
evenWord('aaaa')
> 0

evenWord('potato')
> 2
```

**Solution:**
```js
function evenWord(str) {
 let removeCount = 0;
 let object = {};
 for (var a = 0; a < str.length; a++) {
	if (object[str[a]] == null) {
  	object[str[a]] = 1;
  } else {
  	object[str[a]]++;
  }
 }
  let letterNum = Object.values(object);
   for (var b = 0; b < letterNum.length; b++) {
     if (letterNum[b] % 2 != 0) {
        removeCount++;
      }
    }
 return removeCount;
}
```

