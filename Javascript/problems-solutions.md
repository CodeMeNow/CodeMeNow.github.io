## Problems
### 1. FizzBuzz
Write a program that uses console.log to print all the numbers from 1 to 100 with following exceptions.
* For numbers divisible by 3, print "Fizz" instead of the number
* for numbers divisible by 5 (and not 3) print "Buzz" instead of the number.
* for numbers divisible by both 3 and 5 print "FizzBuzz" instead of the number.
### 2. Print a chessboard
Write a program `printChessBoard` that creates a string that represents an n×n grid, using newline characters to separate lines. At each position of the grid there is either a space or a "#" character.

`printChessBoard(8)` should give the following output.

````
 # # # #
# # # # 
 # # # #
# # # # 
 # # # #
# # # # 
 # # # #
# # # #
````

## Solutions
### 1. FizzBuzz solution

_simple solution_
```` javascript
const fizzbuzz = ()=> {
  for(let i=1; i<=100; i++){
    if(i%15 === 0){
      console.log('FizzBuzz');
    } else if(i%3 === 0){
      console.log('Fizz');
    } else if(i%5 === 0){
      console.log('Buzz');
    } else {
      console.log(i);
    }
  }
}
fizzbuzz();
````
_smart solution_
```` javasctipt
const fizzbuzz = ()=> {
  for(let i=1; i<=100; i++){
    let message = '';
    if(i%3 === 0){
      message = 'Fizz'
    } 
    if(i%5 === 0){
      message += 'Buzz'
    }
    console.log(message || i);
  }
}
fizzbuzz();
````
### 2. View Chessboard solution

```` javascript
const chessBoard = (boardSize) => {
  boardSize = boardSize || 8;
  for(let i=0; i<boardSize; i++){
     let rowMessage = '';
    for(let j=0; j<boardSize; j++){
      if((i+j)%2 === 0){
        rowMessage += ' ';
      } else {
        rowMessage += '#';
      }
    }
    console.log(rowMessage + '\n')
  }
}

chessBoard(16);
````

