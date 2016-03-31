# isJs
Lib to check variable in javascript

## Usage

```javascript
var is = require('isJs');

function B() {}

var table = [
    { a: "Hello", b: new B() },
    { a: "Toto" },
    { a: "Hulul", c: [
        87,
        99,
        52
    ]}
]

var ruleObject = is.object.with.properties({
    a: is.string.match(/^[A-Z]/),
    b: is.object.instanceOf(B).or(is.undefined),
    c: is.array.len.sup(0).and.each(is.number.in.range(0, 100)).or(is.undefined)
})

var ruleTable = is.array.each(ruleObject);

console.log(ruleTable(table)); // true
```