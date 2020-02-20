# Test task

## Javascript:

1. **What is your favourite new javascript feature and why?**

   - Destructuring
   - Because we can extract data from arrays and objects in single line.

2. **Explain an interesting way in which you have used this javascript feature.**

   ```
   const employer = {
       name: 'John',
       lastName: 'Doe'
       job: {
           title: 'developer',
           salary: "$1200"
       }
   }

   ```

   ```
   const { name, lastName, age = 20, job: { title: jobTitle, salary } } = employer;
   ```

   - We can unpact the object(employer) easily
   - We can mutate
   - Nested destructuring(most favourite feature)
   - Also assing a new name to the property like title to jobTitle

3. **Is there any difference between regular function syntax and the shorter arrow function syntax? (Write the answer in your own words)**

   - Yes
   - Regular Functions
     ```
         function fn() {
             // body
         }
     ```
     - Regular functions are created by using function declaration and regular functions are callable and constructible like fn().
     - Its own bindings to the this, arguments etc.
   - Arrow Functions
     ```
         const fn = () => {
             // body
         }
     ```
     - While arrow functions are not its own bindings.
     - Arrow functions are only callable.

4. **What is the difference between ‘myFunctionCall(++foo)’ and ‘myFunctionCall(foo++)’**

   - myFunctionCall(++foo)
     - The parameter(foo++) in above function will increase by one with function call.
   - myFunctionCall(foo++)
     - The parameter(++foo) in above function will increase by one after function call.

5. **In your own words, explain what a javascript ‘class’ is and how it differs from a function.**
   - Javascript classes
   - These are actually type javascript functions
   - We use class keyword to declare a class While functions in javascript are declared with function keyword
   - We can wrap multiple functions in a class
