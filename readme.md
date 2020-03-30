# Hedgehog-matrix

**Hedgehog-matrix** is a library for JavaScript with sweet operator-overload syntax supported by Babel.


### Setup

To use in Node.js, please 
```
npm install Hedgehog-matrix
```
Also install Babel and babel-plugin-overload

### Quick start

```
// Import matrix class from library
import {Mat} from 'hedgehog-matrix';        

// Initialize a new matrix
//  1  ,  2
//  3  ,  4
var a = new Mat([[1,2], [3,4]]);

// Clone matrix A to B
var b = a.clone();

// Matrix manipulation:
// c = a + b*2 + 10
var c = a+b*2+10;

// d = ( a * b - a ) * 0.5
var d = (a*b-a)*0.5

// initialize a matrix e as: 
// 1,2,3
// 4,5,6
// 7,8,9
var e = new Mat()     // initialize new empty matrix
     .range(1, 10)    // initialize as a 9*1 matrix with all elements [1,10)
     .reshape(3 ,3);  // reshape the matrix into a 3*3 matrix


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

// Print Matrix C
console.log("c is " + c)
```