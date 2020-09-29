# Promise

``` javascript
function isPromise(obj) {
  return !!obj && (typeof obj === 'object' || typeof obj === 'function') && typeof obj.then === 'function';
}
```

``` javascript
Promise.prototype.all = function (arr) {
  return new Promise((resolve, reject) => {
    let result = []
    let count = 0
    for (let i = 0; i < arr.length; i++) {
      if (isPromise(arr[i])) {
        arr.then(data => {
          count++
          result[i] = data
          if (count === arr.length) {
            resolve(result)
          }
        }).catch(err => {
          reject(err)
        })
      } else {
        count++
        result[i] = arr[i]
      }
    }
  })
}
```
