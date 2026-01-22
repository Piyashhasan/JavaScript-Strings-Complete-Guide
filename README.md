<!-- Banner (replace with your image if available) -->
<p align="center">
  <img src="https://dmitripavlutin.com/static/6e9e669f0116558d45b32546ed5f5689/59014/cover-2.png" />
</p>

<h1 align="center">🎯 JavaScript Strings - Complete Guide</h1>

> ✅ **Author**: [Piyash Hasan](https://github.com/piyashhasan)  
> 📝 **Topic**: All About javaScript String </br>
> 📅 **Published**: 22 January 2026

> A comprehensive guide to mastering strings in JavaScript - from basics to advanced techniques. Perfect for developers at all levels! 🚀

---

## 📚 Table of Contents

- [String Definition](#-string-definition)
- [How to Define Strings](#-how-to-define-strings)
- [Escape Characters](#-escape-characters)
- [String Interpolation](#-string-interpolation)
- [String Methods](#️-string-methods)
- [Search Methods](#-search-methods)
- [String Comparison](#-string-comparison)
- [Type Conversion](#-type-conversion)
- [Best Practices](#-best-practices)
- [Contributing](#-contributing)

---

## 📖 String Definition

A **string** in JavaScript is a sequence of characters used to represent text. Strings are **immutable**, meaning once created, they cannot be changed. Any operation that appears to modify a string actually creates a new string.

```javascript
const message = "Hello, World!";
console.log(typeof message); // "string"
```

**Key Points:**

- Strings can contain letters, numbers, symbols, and spaces
- Strings are indexed starting from 0
- Strings are primitive data types in JavaScript

---

## 🔧 How to Define Strings

JavaScript provides three ways to create strings:

### 1️⃣ Single Quotes (`'`)

```javascript
const greeting = "Hello, Developer!";
const name = "Alice";
const quote = 'She said, "JavaScript is awesome!"';
```

### 2️⃣ Double Quotes (`"`)

```javascript
const greeting = "Hello, Developer!";
const name = "Bob";
const quote = "It's a beautiful day!";
```

### 3️⃣ Template Literals (Backticks `` ` ``)

```javascript
const name = "Charlie";
const age = 25;

// Single line
const intro = `My name is ${name} and I am ${age} years old.`;

// Multi-line
const poem = `
  Roses are red,
  Violets are blue,
  JavaScript is awesome,
  And so are you!
`;

// Expression evaluation
const result = `The sum is: ${10 + 20}`; // "The sum is: 30"
```

**Comparison:**

| Feature       | Single/Double Quotes | Template Literals |
| ------------- | -------------------- | ----------------- |
| Interpolation | ❌ No                | ✅ Yes            |
| Multi-line    | ❌ No                | ✅ Yes            |
| Expressions   | ❌ No                | ✅ Yes            |

---

## 🔐 Escape Characters

Escape characters allow you to include special characters in strings using a backslash (`\`).

```javascript
// Common escape sequences
const newLine = "First Line\nSecond Line";
const tab = "Column1\tColumn2";
const backslash = "This is a backslash: \\";
const quote = 'He said, "Hello!"';
const singleQuote = "It's working!";
const carriageReturn = "Text\rNew";
const unicode = "\u0048\u0065\u006C\u006C\u006F"; // "Hello"
const hexadecimal = "\x48\x69"; // "Hi"
```

**Common Escape Characters:**

| Sequence | Description       |
| -------- | ----------------- |
| `\n`     | New line          |
| `\t`     | Tab               |
| `\\`     | Backslash         |
| `\'`     | Single quote      |
| `\"`     | Double quote      |
| `\r`     | Carriage return   |
| `\b`     | Backspace         |
| `\f`     | Form feed         |
| `\uXXXX` | Unicode character |

---

## 💡 String Interpolation

Template literals support **string interpolation** - embedding variables and expressions directly into strings.

```javascript
const firstName = "John";
const lastName = "Doe";
const age = 30;

// Variable interpolation
const fullName = `${firstName} ${lastName}`;

// Expression interpolation
const info = `${firstName} is ${age > 18 ? "an adult" : "a minor"}`;

// Function calls
const greeting = `Hello, ${firstName.toUpperCase()}!`;

// Nested template literals
const message = `User: ${`${firstName} ${lastName}`.toUpperCase()}`;

// Multi-line with interpolation
const profile = `
  Name: ${firstName} ${lastName}
  Age: ${age}
  Status: ${age >= 18 ? "Adult" : "Minor"}
`;
```

---

## 🛠️ String Methods

JavaScript strings come with many built-in methods for manipulation and transformation.

### 📏 `length`

Returns the number of characters in a string (property, not a method).

```javascript
const text = "JavaScript";
console.log(text.length); // 10

const empty = "";
console.log(empty.length); // 0
```

---

### 🔤 `charAt(index)`

Returns the character at the specified index.

```javascript
const str = "JavaScript";
console.log(str.charAt(0)); // "J"
console.log(str.charAt(4)); // "S"
console.log(str.charAt(100)); // "" (empty string)
```

---

### 🔢 `charCodeAt(index)`

Returns the Unicode value of the character at the specified index.

```javascript
const str = "ABC";
console.log(str.charCodeAt(0)); // 65
console.log(str.charCodeAt(1)); // 66
console.log(str.charCodeAt(2)); // 67
```

---

### 🌟 `codePointAt(index)`

Returns the Unicode code point value at the given index (handles emojis better).

```javascript
const str = "😀ABC";
console.log(str.codePointAt(0)); // 128512 (emoji code point)
console.log(str.codePointAt(2)); // 65 (A)

// Comparison with charCodeAt
console.log(str.charCodeAt(0)); // 55357 (only first part of emoji)
```

---

### ➕ `concat(str1, str2, ...)`

Joins two or more strings together.

```javascript
const str1 = "Hello";
const str2 = "World";
console.log(str1.concat(" ", str2)); // "Hello World"
console.log(str1.concat(" ", str2, "!")); // "Hello World!"

// Multiple strings
const result = "Java".concat("Script", " is", " awesome");
// "JavaScript is awesome"
```

---

### 🎯 `at(index)`

Returns the character at the specified index (supports negative indexing).

```javascript
const str = "JavaScript";
console.log(str.at(0)); // "J"
console.log(str.at(-1)); // "t" (last character)
console.log(str.at(-2)); // "p"
console.log(str.at(100)); // undefined
```

---

### ✂️ `slice(start, end)`

Extracts a section of a string and returns it as a new string.

```javascript
const str = "JavaScript";
console.log(str.slice(0, 4)); // "Java"
console.log(str.slice(4)); // "Script"
console.log(str.slice(-6)); // "Script"
console.log(str.slice(-6, -2)); // "Scri"
console.log(str.slice(4, 10)); // "Script"
```

---

### 📝 `substring(start, end)`

Similar to `slice()`, but doesn't accept negative indexes.

```javascript
const str = "JavaScript";
console.log(str.substring(0, 4)); // "Java"
console.log(str.substring(4)); // "Script"
console.log(str.substring(4, 10)); // "Script"

// Negative values treated as 0
console.log(str.substring(-3)); // "JavaScript"

// If start > end, they are swapped
console.log(str.substring(4, 0)); // "Java"
```

---

### 🔠 `toUpperCase()`

Converts all characters to uppercase.

```javascript
const str = "hello world";
console.log(str.toUpperCase()); // "HELLO WORLD"

const mixed = "JavaScript";
console.log(mixed.toUpperCase()); // "JAVASCRIPT"
```

---

### 🔡 `toLowerCase()`

Converts all characters to lowercase.

```javascript
const str = "HELLO WORLD";
console.log(str.toLowerCase()); // "hello world"

const mixed = "JavaScript";
console.log(mixed.toLowerCase()); // "javascript"
```

---

### 🧹 `trim()`

Removes whitespace from both ends of a string.

```javascript
const str = "   Hello World   ";
console.log(str.trim()); // "Hello World"

// Also removes newlines and tabs
const messy = "\n\t  JavaScript  \t\n";
console.log(messy.trim()); // "JavaScript"

// trimStart() / trimLeft() - removes from start
console.log(str.trimStart()); // "Hello World   "

// trimEnd() / trimRight() - removes from end
console.log(str.trimEnd()); // "   Hello World"
```

---

### ⬅️ `padStart(length, padString)`

Pads the string from the start until it reaches the specified length.

```javascript
const str = "5";
console.log(str.padStart(3, "0")); // "005"

const code = "42";
console.log(code.padStart(5, "0")); // "00042"

// Credit card formatting
const last4 = "1234";
console.log(last4.padStart(16, "*")); // "************1234"
```

---

### ➡️ `padEnd(length, padString)`

Pads the string from the end until it reaches the specified length.

```javascript
const str = "5";
console.log(str.padEnd(3, "0")); // "500"

const name = "John";
console.log(name.padEnd(10, ".")); // "John......"

// Table formatting
const price = "25";
console.log(price.padEnd(10, " ") + "USD"); // "25        USD"
```

---

### 🔁 `repeat(count)`

Returns a new string with the specified number of copies.

```javascript
const str = "Ha";
console.log(str.repeat(3)); // "HaHaHa"

const dash = "-";
console.log(dash.repeat(20)); // "--------------------"

// Creating patterns
const pattern = "🌟".repeat(5); // "🌟🌟🌟🌟🌟"
```

---

### 🔄 `replace(searchValue, newValue)`

Replaces the **first occurrence** of a substring or pattern.

```javascript
const str = "Hello World, Hello Universe";
console.log(str.replace("Hello", "Hi"));
// "Hi World, Hello Universe"

// With regex (global flag for all occurrences)
console.log(str.replace(/Hello/g, "Hi"));
// "Hi World, Hi Universe"

// Case-insensitive
console.log(str.replace(/hello/i, "Hi"));
// "Hi World, Hello Universe"

// Using function
const result = "I have 2 apples".replace(/\d+/, (match) => {
  return parseInt(match) * 2;
});
console.log(result); // "I have 4 apples"
```

---

### 🔄 `replaceAll(searchValue, newValue)`

Replaces **all occurrences** of a substring or pattern.

```javascript
const str = "Hello World, Hello Universe";
console.log(str.replaceAll("Hello", "Hi"));
// "Hi World, Hi Universe"

// With regex (must have global flag)
console.log(str.replaceAll(/Hello/g, "Hi"));
// "Hi World, Hi Universe"

// Replace all spaces
const text = "a b c d";
console.log(text.replaceAll(" ", "-")); // "a-b-c-d"
```

---

### ✂️ `split(separator, limit)`

Splits a string into an array of substrings.

```javascript
const str = "apple,banana,orange";
console.log(str.split(","));
// ["apple", "banana", "orange"]

// Split by space
const sentence = "Hello World";
console.log(sentence.split(" "));
// ["Hello", "World"]

// Split into characters
console.log("Hello".split(""));
// ["H", "e", "l", "l", "o"]

// With limit
console.log(str.split(",", 2));
// ["apple", "banana"]

// Split by regex
const text = "one1two2three3";
console.log(text.split(/\d/));
// ["one", "two", "three", ""]
```

---

### ✅ `isWellFormed()`

Checks if the string contains any lone surrogate characters.

```javascript
const wellFormed = "Hello 😀";
console.log(wellFormed.isWellFormed()); // true

const loneHigh = "ab\uD800cd";
console.log(loneHigh.isWellFormed()); // false

const loneLow = "ab\uDC00cd";
console.log(loneLow.isWellFormed()); // false
```

---

### 🔧 `toWellFormed()`

Returns a string where any lone surrogates are replaced with the Unicode replacement character (�).

```javascript
const loneHigh = "ab\uD800cd";
console.log(loneHigh.toWellFormed()); // "ab�cd"

const loneLow = "ab\uDC00cd";
console.log(loneLow.toWellFormed()); // "ab�cd"

const normal = "Hello 😀";
console.log(normal.toWellFormed()); // "Hello 😀"
```

---

## 🔍 Search Methods

Methods for searching and finding substrings within strings.

### 📍 `indexOf(searchValue, fromIndex)`

Returns the index of the **first occurrence** of a substring, or -1 if not found.

```javascript
const str = "Hello World, Hello Universe";
console.log(str.indexOf("Hello")); // 0
console.log(str.indexOf("World")); // 6
console.log(str.indexOf("Hello", 5)); // 13 (search from index 5)
console.log(str.indexOf("Goodbye")); // -1 (not found)

// Case-sensitive
console.log(str.indexOf("hello")); // -1
```

---

### 📍 `lastIndexOf(searchValue, fromIndex)`

Returns the index of the **last occurrence** of a substring.

```javascript
const str = "Hello World, Hello Universe";
console.log(str.lastIndexOf("Hello")); // 13
console.log(str.lastIndexOf("o")); // 17
console.log(str.lastIndexOf("Hello", 10)); // 0 (search backwards from index 10)
console.log(str.lastIndexOf("Goodbye")); // -1
```

---

### 🔎 `search(regexp)`

Searches for a match using a regular expression and returns the index.

```javascript
const str = "Hello World 123";
console.log(str.search("World")); // 6
console.log(str.search(/\d+/)); // 12 (finds numbers)
console.log(str.search(/world/i)); // 6 (case-insensitive)
console.log(str.search(/goodbye/)); // -1

// Unlike indexOf, search() accepts regex
const text = "The price is $50";
console.log(text.search(/\$\d+/)); // 13
```

---

### 🎯 `match(regexp)`

Retrieves the matches when matching a string against a regular expression.

```javascript
const str = "The rain in Spain stays mainly in the plain";

// Without global flag - returns first match with details
console.log(str.match(/ain/));
// ["ain", index: 5, input: "The rain in Spain...", groups: undefined]

// With global flag - returns all matches
console.log(str.match(/ain/g));
// ["ain", "ain", "ain", "ain"]

// No match
console.log(str.match(/xyz/)); // null

// Extract numbers
const text = "I have 2 apples and 5 oranges";
console.log(text.match(/\d+/g)); // ["2", "5"]
```

---

### 🎯 `matchAll(regexp)`

Returns an iterator of all matches (regexp must have global flag).

```javascript
const str = "test1 test2 test3";
const matches = str.matchAll(/test(\d)/g);

for (const match of matches) {
  console.log(`Found ${match[0]} with number ${match[1]}`);
}
// Found test1 with number 1
// Found test2 with number 2
// Found test3 with number 3

// Convert to array
const allMatches = [...str.matchAll(/test(\d)/g)];
console.log(allMatches.length); // 3
```

---

### ✔️ `includes(searchString, position)`

Checks if a string contains a specified substring.

```javascript
const str = "Hello World";
console.log(str.includes("World")); // true
console.log(str.includes("world")); // false (case-sensitive)
console.log(str.includes("Hello", 5)); // false (search from index 5)
console.log(str.includes("o")); // true

// Practical use
const email = "user@example.com";
if (email.includes("@")) {
  console.log("Valid email format");
}
```

---

### 🎬 `startsWith(searchString, position)`

Checks if a string starts with a specified substring.

```javascript
const str = "Hello World";
console.log(str.startsWith("Hello")); // true
console.log(str.startsWith("World")); // false
console.log(str.startsWith("World", 6)); // true (check from index 6)
console.log(str.startsWith("hello")); // false (case-sensitive)

// Practical use
const url = "https://example.com";
if (url.startsWith("https://")) {
  console.log("Secure connection");
}
```

---

### 🎬 `endsWith(searchString, length)`

Checks if a string ends with a specified substring.

```javascript
const str = "Hello World";
console.log(str.endsWith("World")); // true
console.log(str.endsWith("Hello")); // false
console.log(str.endsWith("Hello", 5)); // true (check first 5 characters)

// Practical use
const filename = "document.pdf";
if (filename.endsWith(".pdf")) {
  console.log("PDF file detected");
}
```

---

## ⚖️ String Comparison

Comparing strings in JavaScript.

```javascript
// Using comparison operators
console.log("apple" === "apple"); // true
console.log("Apple" === "apple"); // false (case-sensitive)
console.log("apple" < "banana"); // true (lexicographical)
console.log("10" < "2"); // true (string comparison, not numeric)

// localeCompare() - for proper sorting
const str1 = "apple";
const str2 = "banana";
console.log(str1.localeCompare(str2)); // -1 (str1 comes before str2)
console.log(str2.localeCompare(str1)); // 1 (str2 comes after str1)
console.log(str1.localeCompare(str1)); // 0 (equal)

// Case-insensitive comparison
const a = "Hello";
const b = "hello";
console.log(a.toLowerCase() === b.toLowerCase()); // true
```

---

## 🔄 Type Conversion

Converting between strings and other types.

### String to Number

```javascript
// Using Number()
console.log(Number("123")); // 123
console.log(Number("12.34")); // 12.34
console.log(Number("abc")); // NaN

// Using parseInt()
console.log(parseInt("123")); // 123
console.log(parseInt("123.99")); // 123
console.log(parseInt("123abc")); // 123
console.log(parseInt("abc")); // NaN

// Using parseFloat()
console.log(parseFloat("12.34")); // 12.34
console.log(parseFloat("12")); // 12

// Using unary +
console.log(+"123"); // 123
console.log(+"12.5"); // 12.5
```

### Number to String

```javascript
const num = 123;

// Using toString()
console.log(num.toString()); // "123"

// Using String()
console.log(String(num)); // "123"

// Using template literals
console.log(`${num}`); // "123"

// Using concatenation
console.log(num + ""); // "123"

// toFixed() for decimals
const price = 19.99;
console.log(price.toFixed(2)); // "19.99"
```

### Other Conversions

```javascript
// Boolean to String
console.log(String(true)); // "true"
console.log(String(false)); // "false"

// Array to String
const arr = [1, 2, 3];
console.log(arr.toString()); // "1,2,3"
console.log(arr.join("-")); // "1-2-3"

// Object to String
const obj = { name: "John" };
console.log(obj.toString()); // "[object Object]"
console.log(JSON.stringify(obj)); // '{"name":"John"}'
```

---

## ✨ Best Practices

### 1. Choose the Right String Syntax

```javascript
// ✅ Good: Use template literals for interpolation
const name = "Alice";
const greeting = `Hello, ${name}!`;

// ❌ Avoid: Concatenation for dynamic strings
const greeting2 = "Hello, " + name + "!";

// ✅ Good: Use single/double quotes for static strings
const message = "Hello World";
```

### 2. Be Aware of Immutability

```javascript
// Strings are immutable
let str = "Hello";
str[0] = "h"; // This doesn't work
console.log(str); // Still "Hello"

// ✅ Create new strings instead
str = "h" + str.slice(1); // "hello"
```

### 3. Use Appropriate Search Methods

```javascript
// ✅ Use includes() for simple checks
if (str.includes("keyword")) {
}

// ✅ Use startsWith/endsWith for position checks
if (url.startsWith("https://")) {
}

// ✅ Use regex for complex patterns
if (/^\d{3}-\d{3}-\d{4}$/.test(phoneNumber)) {
}
```

### 4. Handle Empty and Null Values

```javascript
const str = "";

// ✅ Check for empty strings
if (str.length === 0) {
}
if (str === "") {
}
if (!str) {
} // Also catches null/undefined

// ✅ Provide defaults
const value = str || "default value";
const value2 = str ?? "default value"; // nullish coalescing
```

### 5. Performance Considerations

```javascript
// ✅ Use join() for building strings from arrays
const parts = ["Hello", "World"];
const result = parts.join(" "); // Faster

// ❌ Avoid repeated concatenation in loops
let result2 = "";
for (let i = 0; i < 1000; i++) {
  result2 += "text"; // Slower
}
```

---

## 🤝 Contributing

Contributions are welcome! If you find any errors or want to add more examples:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 🌟 Show Your Support

If you found this guide helpful, please give it a ⭐️!

---

## 📞 Connect

- **GitHub:** [Piyash Hasan](https://github.com/Piyashhasan)
- **LinkedIn:** [Piyash Hasan](https://www.linkedin.com/in/piyashhasan/)

---

<div align="center">
  <strong>Happy Coding! 🚀</strong>
  <br>
  Made with ❤️ by JavaScript Developers
</div>
