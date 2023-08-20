---
share: true
---
.shift() is the opposite of the .pop() method which deletes the first element.
.unshift(x) is the opposite of the .push(x) method which adds the first element


const anotherObject = {
  make: "Ford",
  5: "five",
  "model": "focus"
};
 <JS automatically type casts these keys>

If the property of the object you are trying to access has a space in its name, you will need to use bracket notation.
myObj["Space Name"];

Javascript allows Objects as Pass by reference, so the references share the same object and the changes made by one reference is reflected permanently in the main object that has been created. 