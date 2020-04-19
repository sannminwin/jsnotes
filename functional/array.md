### Array Manipulation

#### 1. Find intersection between two arrays

##### a. Using for loop

```js
function arr_diff (a1, a2) {

    var a = [], diff = [];
    for (var i = 0; i < a1.length; i++) {
        a[a1[i]] = true;
    }
    for (var i = 0; i < a2.length; i++) {
        if (a[a2[i]]) {
            delete a[a2[i]];
        } else {
            a[a2[i]] = true;
        }
    }
    for (var k in a) {
        diff.push(k);
    }
    return diff;
}

console.log(arr_diff(['a', 'b'], ['a', 'b', 'c', 'd']));
console.log(arr_diff("abcd", "abcde"));
console.log(arr_diff("zxc", "zxc"));
```

##### b. Using ES7

```js
let intersection = arr1.filter(x => arr2.includes(x));
```


#### 2. Find difference between two arrays
##### a. Using ES7

```js
let difference = arr1
    .filter(x => !arr2.includes(x))
    .concat(arr2.filter(x => !arr1.includes(x)));
```

