# Lists and Links

### In Javascript, you want to create a new array from an available array by converting each element of the original array to create the corresponding element of the new array, you can use map() method. 
  ##### For simplicity, please see the example, you have an array of integer numbers, such as [1, 2, 5], and you want to create another array by multiplying each element of the initial array by 10.


  ```
  var arr1 = [1, 2, 5];
 
console.log(arr1); // --> [1, 2, 5]
 
var arr2 = arr1.map( e  => e * 10 );
 
console.log(arr2); // --> [10, 20, 50]
  ```
  ![](https://s1.o7planning.com/en/12135/images/25394275.png)

  2- React Keys

#### Keys helps React distinguish items in a list. It helps the React manage the changed items, new items added, or items removed from the list.
###### From an array of objects, you create a new array containing tags, which should have the key attribute, and their values are not allowed to be the same.
![](https://s1.o7planning.com/en/12135/images/25396630.png)

# JS spread operator
Spread operator allows an iterable to expand in places where 0+ arguments are expected. It is mostly used in the variable array where there is more than 1 values are expected. It allows us the privilege to obtain a list of parameters from an array. Syntax of Spread operator is same as Rest parameter but it works completely opposite of it.
![](https://media.geeksforgeeks.org/wp-content/uploads/20190220151444/Screenshot-2110.png)
**thing can spread operator do!**

- Copying an array.
- Concatenating or combining arrays.
- Using Math functions.
- Using an array as arguments.
- Adding an item to a list.
- Adding to state in React.
- Combining objects.
- Converting NodeList to an array.


```
merge two arrays 

let fruits = ["apples", "bananas"];
let vegetables = ["corn", "carrots"];
let produce = [...fruits, ...vegetables];
//["apples","bananas","corn","carrots"]
```


```
add to array:

var a = [1, 2, 3, 4, 5];
var b = [0].concat(a);

console.log(a);
console.log(b);

```

```
merge two objects 

let person = {
    firstName: 'John',
    lastName: 'Doe',
    age: 25,
    ssn: '123-456-2356'
};


let job = {
    jobTitle: 'JavaScript Developer',
    location: 'USA'
};

let employee = {
    ...person,
    ...job
};

console.log(employee);

```

In the video, what is the first step that the developer does to pass functions between components?
- He made a function to pass through the objects.

In your own words, what does the increment function do?
- the increment function will go through the objects if the name will be the same it will return as an array and counts again.

How can you pass a method from a parent component into a child component?
- methodName={this.methodName }

How does the child component invoke a method that was passed to it from a parent component?
- this.props.methodName()