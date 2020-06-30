# Array Exchange and Reversing

It's time for some array exchange! The objective is simple: exchange the elements of two arrays in-place in a way that their new content is also reversed.

```
// before
const myArray = ['a', 'b', 'c'];
const otherArray = [1, 2, 3];

exchangeWith(myArray, otherArray);

// after
myArray => [3, 2, 1]
otherArray => ['c', 'b', 'a']
```

# Solution 

```
function exchangeWith(a, b) {
  // your code here
  let temp = JSON.parse(JSON.stringify(a))
  a.splice(0, a.length, ...b.reverse())
  b.splice(0, b.length, ...temp.reverse())
}
```
