<p align="center">
   Hello there! This is my JavaScript-StyleGuide
</p>


# _JavaScript-StyleGuide_ 
+ Always use the same coding conventions for all your JavaScript projects.


<p align="center">
  <img src="https://i.pinimg.com/564x/34/43/b1/3443b136a4f238c30802fa0dcb374932.jpg"/>
</p>


## _1. Variable Names_
#### Always use `camelCase` for identifier names (variables and functions). In addition, it's a best practice to actually tell what the function is doing by giving the function name a verb as prefix.
```
// bad
let Firstname = 'Robin';
// bad
function name(firstName, lastName) {
  return `${firstName} ${lastName}`;
}
// good
let firstName = 'Robin';
// good
function getName(firstName, lastName) {
  return `${firstName} ${lastName}`;
}
```

## _2. Semicolons ARE required_
Every statement must be terminated with a semicolon. Relying on automatic semicolon insertion is forbidden.
```
// bad
let lavinia = {}
let ilia = {}
[lavinia, ilia].forEach(jedi => jedi.father = 'vader')
// good
let lavinia = {};
let ilia = {};
[lavinia, ilia].forEach((jedi) => {  
  jedi.father = 'vader';
});
```

## _3. Don’t use var anymore_
Declare all local variables with either `const` or `let`.
```
// bad
var example = 42;
// good
let example = 42;
```

## _4. Arrow functions are preferred_
Arrow functions provide a concise syntax and fix a number of difficulties with `this`. Prefer arrow functions over the function keyword, particularly for nested functions.
```
// bad
[1, 2, 3].map(function (x) {  
  const y = x + 1;  
  return x * y;
});
// good
[1, 2, 3].map((x) => {
  const y = x + 1;
  return x * y;
});
```

## _5. Use template strings instead of concatenation_
Use template strings (delimited with \`\ ) over complex string concatenation, particularly if multiple string literals are involved. Template strings may span multiple lines.
```
// bad
function sayHi(name) {  
  return 'How are you, ' + name + '?';
}
// bad
function sayHi(name) {  
  return ['How are you, ', name, '?'].join();
}
// bad
function sayHi(name) {  
  return `How are you, ${ name }?`;
}
// good
function sayHi(name) {  
  return `How are you, ${name}?`;
};
```

## _6. Constants should be named in ALL_UPPERCASE separated by underscores_
Constant names use CONSTANT_CASE: all uppercase letters, with words separated by underscores.
```
// bad
const number = 5;
// good
const NUMBER = 5;
```

## _7. One variable per declaration_
Every local variable declaration declares only one variable: declarations such as let a = 1, b = 2; are not used.
```
// bad
let a = 1, b = 2, c = 3;
// good
let a = 1;
let b = 2;
let c = 3;
```

## _8. Use single quotes, not double quotes_
Ordinary string literals are delimited with single quotes ('), rather than double quotes (").
Tip: if a string contains a single quote character, consider using a template string to avoid having to escape the quote.
```
// bad
let directive = "No identification of self or mission."
// bad
let saying = 'Say it ain\u0027t so.';
// good
let directive = 'No identification of self or mission.';
// good
let saying = `Say it ain't so`;
```

## _9. Quotes_
Whether you prefer single or double shouldn't matter, there is no difference in how JavaScript parses them. What ABSOLUTELY MUST be enforced is consistency. Never mix quotes in the same project. Pick one style and stick with it.

## _10. One `const` or `let` statement must be used per variable assignment. These must be declared at the top of the function in which they are being used._
```
// bad:
var good = 'string',
iffy = [
'hmm', 'not', 'great'
];

// good:
const good = 'string';
const alsoGood = 'another';

// good:
const good = 'string';
const okay = [
'hmm', 'a bit', 'better'
];
```
