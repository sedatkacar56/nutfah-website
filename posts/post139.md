In JAVASCRIPT NO DIFFERENTIATION between Different Number types!!!! (Bye bye float, double, integers.....)

What is the Number type in JavaScript?

In JavaScript, all numbers are represented by a single data type called Number. Unlike many languages (like Java, C, or Python) that separate:
- integers
- floating-point numbers
- long numbers

👉 JavaScript uses ONE unified type: number.

This means:
- whole numbers
- decimal numbers
- negative numbers
- special numeric values
are all of type number.

Different kinds of numbers in JavaScript

JavaScript Number type includes:
- Integers: 42
- Floating-point numbers (decimals): 3.14
- Negative numbers: -7
- Special numeric values: Infinity, -Infinity, NaN // Not a Number

All of these are still number. ✅

Code example (what the question is asking for)

let integerNumber = 10;
let decimalNumber = 3.14;
let negativeNumber = -25;
let infinityNumber = Infinity;
let notANumber = NaN;

console.log(typeof integerNumber); // number
console.log(typeof decimalNumber); // number
console.log(typeof negativeNumber); // number
console.log(typeof infinityNumber); // number
console.log(typeof notANumber); // number (is this a number??? Wow!!!)

✅ Output shows that all numeric values are of type number.

🔑 Key takeaway (important)

JavaScript does not have separate types for integers and floats. Everything numeric falls under the number type. This design makes JavaScript simpler to use, but it also means you need to be careful with:
- precision (e.g. 0.1 + 0.2)
- NaN behavior
- very large numbers

#JavaScript #JavaScriptBasics #Programming #WebDevelopment #Coding #LearnToCode #SoftwareDevelopment #TechLearning #ComputerScience #FrontendDevelopment #CodeNewbie #DevCommunity #AlCamil
