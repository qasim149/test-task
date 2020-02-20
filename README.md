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
   - These are actually type of javascript functions
   - We use class keyword to declare a class While functions in javascript are declared with function keyword
   - We can wrap multiple functions in a class

## CSS:

6. **In your own words, explain css specificity**

   - If there are two or more conflicting CSS rules that point to the same element, the browser follows some rules to determine which one is most specific and therefore wins out.
   - Think of specificity as a score/rank that determines which style declarations are ultimately applied to an element.
   - The universal selector (\*) has low specificity, while ID selectors are highly specific!

7. **In your own words, explain, what is ‘!important’ in css. Also how does it work? Are there any special circumstances when using it, where it’s behaviour might not be what you expect?**

   - It means, essentially, what it says; that 'this is important, ignore subsequent rules, and any usual specificity issues, apply this rule!'
   - In normal use a rule defined in an external stylesheet is overruled by a style defined in the head of the document, which, in turn, is overruled by an in-line style within the element itself (assuming equal specificity of the selectors). Defining a rule with the `!important` 'attribute' (?) discards the normal concerns as regards the 'later' rule overriding the 'earlier' ones.
   - Also, ordinarily, a more specific rule will override a less-specific rule. So:

   ```
    a {
        /* css */
    }

   ```

   - Is normally overruled by:

   ```
     body div #elementID ul li a {
        /* css */
    }
   ```

8. **What is your prefered layout system: inline-block, floating + clearing, flex, grid, other? And why?**

   - I will prefered `inline-block`
   - Because It has been possible for a long time to create a grid of boxes that fills the browser width and wraps nicely (when the browser is resized), by using the float property. However, the `inline-block` value of the display property makes this even easier. `inline-block` elements are like inline elements but they can have a width and a height.

9. **Are negative margins legal and what do they do (margin: -20px)?**

   - Some how its legal.
   - controls the amount of space between an element's border and surrounding elements. If you set an element's margin to a negative value, the element will grow larger.

10. **If a <div/> has no margin or other styling and a <p/> tag inside of it has a margin top of some kind, the margin from the <p/> tag will show up on the div instead (the margin will show above the div not inside of it), why is this? What are the different things that can be done to prevent it?**
    - I think we should add `position: relative;` to the <div/>
