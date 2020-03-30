# Hedgehog-matrix

**Hedgehog-matrix** is a library for JavaScript with sweet operator-overload syntax supported by Babel.


## Setup

To use in Node.js, please 
```
npm install Hedgehog-matrix
```
Also install Babel and babel-plugin-overload

## Quick start

### Initialize a matrix

```JavaScript
// Import matrix class from library
import {Mat} from 'hedgehog-matrix';        

// Initialize a new matrix
//  1  ,  2
//  3  ,  4
var a = new Mat([[1,2], [3,4]]);
```

### Clone matrix A to B
```JavaScript
var b = a.clone();
```

### Matrix manipulation:
```JavaScript
// c = a + b*2 + 10
var c = a+b*2+10;

// d = ( a * b - a ) * 0.5
var d = (a*b-a)*0.5

// x = a'*a
var x = a.T() * a
```

### Matrix utilities
```JavaScript
// initialize a matrix e as: 
// 1,2,3
// 4,5,6
// 7,8,9
var e = new Mat()     // initialize new empty matrix
     .range(1, 10)    // initialize as a 9*1 matrix with all elements [1,10)
     .reshape(3 ,3);  // reshape the matrix into a 3*3 matrix



//zeros
var zeros = new Mat().zeros(10,10);

//ones
var ones = new Mat().ones(10,10);

//identity matrix
var diag_mat = new Mat().identity(10);

//random matrix
var random_mat = new Mat().random(10,10);
```

### Compare operator overload
```JavaScript
// compare a * a with another matrix [[7,10], [15,22]] using operator "=="
if ( a * a == new Mat([
    [7, 10],
    [15,22]]  ) )
{
    console.log("Yay! Operator == works !");
}
else
{
    console.log("Operator == doens't work");
}
```


### Matrix / CSV / JSON convertor

```JavaScript
var x = csv2mat(
    '1,2,3
     4,5,6
     7,8,9');

var y = mat2csv(x);

var json_x = mat2json(x);
var x_from_json = json2mat(json_x);
```
