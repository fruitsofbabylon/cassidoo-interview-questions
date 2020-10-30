# Interview Question of the Week Solutions
My solutions for the 'interview question of the week' section from Cassidy Williams' weekly newsletter. You can subscribe [here](https://cassidoo.co/newsletter/). Done in JavaScript. 
## 4/02/20 Issue #129
Given that an "even word" is a word in which each character appears an even number of times, write a function that takes in a string and returns the minimum number of letters to be removed to make that string an even word.

Example:
```
evenWord('aaaa')
> 0

evenWord('potato')
> 2
```

Solution:
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

## 10/02/20 Issue #130

Given an array of points that represent the 3 vertices of a triangle, and a point K, return true if K is inside the triangle.

Example:
```
let triangle = [ [0,0], [0,3], [4,0] ]

isInTriangle(triangle, [2,1])
> true

isInTriangle(triangle, [3,2])
> false
```

Solution:
```
function isInTriangle(triangle, point) {
  let results = [];
  for (let a = 0; a < triangle.length; a++) {
    let result = null;
    if (a == triangle.length - 1) {
      result = dotProduct([triangle[a], triangle[0]], point);
    } else {
      result = dotProduct([triangle[a], triangle[a+1]], point);
    }
    results.push(result);
  }
  if ((results[0] >= 0 && results[1] >= 0 && results[2] >= 0) || (results[0] <= 0 && results[1] <= 0 && results[2] <= 0)) {
    return true;
  } else {
    return false;
  }
};

function dotProduct(line, point) {
  let [x1, y1] = line[0];
  let [x2, y2] = line[1];
  let side = [x2-x1, y2-y1];
  let perpendicular = [-side[1], side[0]];
  let pointLine = [point[0]-x1, point[1]-y1];
  let product = perpendicular[0] * pointLine[0] + perpendicular[1] * pointLine[1];
  return product;
}
```

