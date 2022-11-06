# Some Of The Common ESLint Errors and their solutions

use object destructuring
> solution: Destructure the Object

```
problem : 
const action = this.state.action;

solution: 
const {action} = this.state;
``` 

import A should occur before import of B or function A should be placed after function B
> 
solution: simply put A on the upper side of B or placed function A after function B.

```
problem : 
import B;
import A;

solution: 
import A;
import B;
``` 

expected a default case
> solution: add a default case whenever you use switch cases

```
problem : 

 switch(expression) {
  case x:
    // code block
    break;
  case y:
    // code block
    break;
}

solution: 

switch(expression) {
  case x:
    // code block
    break;
  case y:
    // code block
    break;
  default:
    // code block
}
``` 

unexpected block statement surrounding arrow body
> solution: Fix arrow-body style problem


```
problem:
 const selectedStudents = studentOptions.find((student) => {
      return student.id === defaultstudentId;
});

solution: 
const selectedStudents = studentOptions.find((student) => student.id === defaultstudentId);
``` 

visible, non-interactive elements with click handlers must have at least one keyboard listener
> solution: you can use something like accessibleOnClick


```
problem:
 <div
        ref={dropdownRef}
        className="d-flex align-items-center pointer"
        onClick={toggleDropdown}
/>

solution: 
<div
        ref={dropdownRef}
        className="d-flex align-items-center pointer"
        {...accessibleOnClick(toggleDropdown)}
/>
``` 

unnecessary else after return
> solution: Remove else condition and return without else condition


```
problem:
compareTwoStrings(A: string, B: string) {
    if (A==B) {
      return true;
    } else {
      return false;
    }
}
solution:
compareTwoStrings(A: string, B: string) {
    if (A==B) {
      return true;
    } 
    return false;
}
Error 7: data is already declared in the upper scope
Solution: Use alternate naming convention
problem: 
 if (err.response instanceof HttpException) {
        const { data, status } = err.response;
        throw new MicroserviceException(data, status);
}

solution: 
if (err.response instanceof HttpException) {
        const { data: errorData, status } = err.response;
        throw new MicroserviceException(errorData, status);
}
``` 

for more information you can visit [es-lint rules](https://eslint.org/docs/rules/)

Happy Coding 😊😊



