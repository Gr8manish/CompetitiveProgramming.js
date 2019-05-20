# Competitive-Programming-JS
**No more boilerplate code to participate in Competitive Programming contests in Node.js * ✨**

[![Build Status](https://travis-ci.org/Gr8manish/CompetitiveProgramming.js.svg?branch=master)](https://travis-ci.org/Gr8manish/CompetitiveProgramming.js) [![dependencies Status](https://david-dm.org/Gr8manish/CompetitiveProgramming.js/status.svg)](https://david-dm.org/Gr8manish/CompetitiveProgramming.js) [![devDependencies Status](https://david-dm.org/Gr8manish/CompetitiveProgramming.js/dev-status.svg)](https://david-dm.org/Gr8manish/CompetitiveProgramming.js?type=dev) [![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)



## Goal 🎯
* This project will help the Node.js Competitive programmers
* Make it easy to debug the code locally
* Provide a utility to wait for user input
* Finally, convert the code, which you can submit on websites like codechef, topcoder, hackerrank, hackerearth etc.

## Installation
1. First, install the package globally :
	```
	npm install -g competitive-programming-js
	```
	**Why?** Global package will let you use **cp-convert** command
2. Now install it locally in the project :
	* Initialize the project (If it's not already NPM project)
		```
		npm init -y
		```
	* Installing the package
		```
		npm install --save competitive-programming-js
		```
	**Why?** Local package will let you use **inputReader** module which wait for user input.

## Basic Use

1. **example.js**
	```javascript
	const {inputReader} = require('competitive-programming-js');

	// To read integer value from console
	let noOfTestCases = inputReader.readInteger();
	console.log(noOfCase,typeof noOfCase);
	while(noOfTestCases--){
		// To read generic array separated by space
		let tmp = inputReader.readArray();
		console.log(tmp, typeof tmp);

		// To read boolean value i.e. 'true' or 'false' (It's case insensitive)
		tmp = inputReader.readBoolean();
		console.log(tmp, typeof tmp);

		// To read a single character
		tmp = inputReader.readChar();
		console.log(tmp, typeof tmp);

		// to read float value
		tmp = inputReader.readFloat();
		console.log(tmp, typeof tmp);

		// to read a line
		tmp = inputReader.readLine();
		console.log(tmp, typeof tmp);

		// To read a numeric array
		tmp = inputReader.readNumberArray();
		console.log(tmp, typeof tmp);
	}
	```

2. Now to convert the file into code which could be submitted on competitive programming websites, run following command:
	* **cp-convert --source example.js --destination output.js**
		OR
	* **cp-convert -s example.js -d output.js**
3. Hurray, that's all. Now you can submit the code which is there in output.js file on any competitive programming website. To learn more in details keep reading :)

## Usage

#### 1. inputReader
##### Ways to import inputReader variable
1. ```javascript 
	const {inputReader} = require('competitive-programming-js'); 
	```
2. ```JavaScript
	const inputReader = require('competitive-programming-js').inputReader;
	```
	**Note:** Currently, only these two are supported.


##### Available functions
> All of these functions will wait for user input
1. readInteger()
	* Get an integer number from the user
	* This can't read the numbers separated by space
	* **Special Case** To read numbers separated by space, you can use following trick:
		```
		// Input = 1 2 3
		let [a,b,c] = inputReader.readNumberArray()
		// After above statement a is 1, b is 2 and c is 3
		```
		**Note** Above code is just using array destructuring

2. readFloat()
	* Get a floating point number from the user
3. readBoolean()
	* Get the true or false value entered by user on the console.
	* 'true' or 'True' or 'TRUE' etc => true (It's case insensitive)
	* 'false' or 'False' or 'FALSE' etc => false (It's case insensitive)
4. readChar()
	* Get a character from the user
5. readLine()
	* Get a string from the user
6. readArray()
	* Get a generic array separated by space
7. readNumberArray()
	* Get a numeric array separated by space

	
#### 2. cp-convert
> It's a global utility which is used to convert the written code into code which is submittable on competitive programming websites
- **Options:**

	| Flags                    | Use                            | Required        |
	| -------------------------|:------------------------------:| :--------------:|
	| --source, -s             | Source file path               | YES             |
	| --destination, --dest, -d| Output file path               |   YES           |
	| --help                   | Show help                       |    -           |
- **Example**
	* **cp-convert --source example.js --destination output.js**
	* **cp-convert -s example.js -d output.js**

# Project Structure

## Used technologies :

* **ES6/ESNext** - Write _ES6_ code and _Babel_ will transpile it to ES5 for backwards compatibility
* **Test** - _Mocha_ with _Istanbul_ coverage
* **Lint** - Preconfigured _ESlint_ with _Airbnb_ config
* **CI** - _TravisCI_ configuration setup
* **Minify** - Built code will be minified for performance

## Commands :
- `npm run clean` - Remove `lib/` directory
- `npm run test` - Run tests with linting and coverage results.
- `npm run test:only` - Run tests without linting or coverage.
- `npm run test:watch` - You can even re-run tests on file changes!
- `npm run test:prod` - Run tests with minified code.
- `npm run test:examples` - Test is written examples on pure JS for better understanding module usage.
- `npm run lint` - Run ESlint with airbnb-config
- `npm run cover` - Get coverage report for your code.
- `npm run build` - Babel will transpile ES6 => ES5 and minify the code.
- `npm run prepublish` - Hook for npm. Do all the checks before publishing your module.

# License

MIT © Manish Menaria
