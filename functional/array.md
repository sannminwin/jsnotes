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

#### 3. Find difference between two object arrays
##### a. Using ES6

```js
const arrayOne = [ 
  { nodeId: "0001", state: "published" },
  { nodeId: "0002", state: "published" },
  { nodeId: "0003", state: "draft" },
  { nodeId: "0004", state: "archieved" },
  { nodeId: "0005", state: "wait_for_review" },
];
          
const arrayTwo = [
  { nodeId: "0001", state: "published"},
  { nodeId: "0002", state: "published"},
  { nodeId: "0003", state: "draft"},
  { nodeId: "0004", state: "archieved"},
];

const results = arrayOne.filter(({ nodeId: id1 }) => !arrayTwo.some(({ nodeId: id2 }) => id2 === id1));

console.log(results);
```

#### 4. Sort array of object numerically by value of a property

##### a. Vanilla JS

```js
const deliveryRate = [
    {
        "city": "Dallas",
        "state": "TX",
        "zip": "75201",
        "price": "162500"
    }, {
        "city": "Bevery Hills",
        "state": "CA",
        "zip": "90210",
        "price": "319250"
    }, {
        "city": "New York",
        "state": "NY",
        "zip": "00010",
        "price": "962500"
    }
];

deliveryRate.sort(function(a, b) {
    return parseFloat(a.price) - parseFloat(b.price);
});

```

##### a. ES6 Version

```js
const deliveryRate = [
    {
        "city": "Dallas",
        "state": "TX",
        "zip": "75201",
        "price": "162500"
    }, {
        "city": "Bevery Hills",
        "state": "CA",
        "zip": "90210",
        "price": "319250"
    }, {
        "city": "New York",
        "state": "NY",
        "zip": "00010",
        "price": "962500"
    }
];

deliveryRate.sort((a, b) => parseFloat(a.price) - parseFloat(b.price));

```