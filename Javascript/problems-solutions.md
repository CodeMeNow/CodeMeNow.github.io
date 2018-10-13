## Problems
### 1.FizzBuzz
Write a program that uses console.log to print all the numbers from 1 to 100 with following exceptions.
* For numbers divisible by 3, print "Fizz" instead of the number
* for numbers divisible by 5 (and not 3) print "Buzz" instead of the number.
* for numbers divisible by bothe 3 and 5 print "FizzBuzz" instead of the number.


## Solutions
<details>
<summary>
  1. View FizzBuzz solution
</summary>


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
</details>

