# Interview Question of the Week Solutions
Solutions for the 'interview question of the week' section from Cassidy Williams' weekly newsletter. You can subscribe [here](https://cassidoo.co/newsletter/). Done in javaScript. 
## 4/02/20 Issue
Given that an "even word" is a word in which each character appears an even number of times, write a function that takes in a string and returns the minimum number of letters to be removed to make that string an even word.

**Solution:**
```js
function removeCharCount (str) {
 let removeCount = 0;
 let letterCount = 0;
 for (var a = 0; a <= str.length; a++) {
 	for (var b = 0; b <= str.length; b++) {
   if (str[a] == str[b]) {
   	letterCount++;
   }
  }
  if (letterCount > 1 && letterCount % 2 != 0) {
  	removeCount++
  }
 }
 return removeCount;
}
```

