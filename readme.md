# Phone Number Formats

Easy way to format and convert phone numbers now with **method chaining and custom types**

## Install

```bash
$ npm install phone-number-formats
```

## Usage

```js
const phoneNumberFormatter = require('phone-number-formats');

let home = new phoneNumberFormatter('1234567').format();
// 123-4567

let work = new phoneNumberFormatter('3-141-592-6535').format({type: 'domestic'});
// (141) 592-6535

let boss = new phoneNumberFormatter('18008675309').format({type: 'international', separator: '.'});
// +1.800.867.5309

let drew = new phoneNumberFormatter('+1 (800) 271-WHAT').format({type: 'international', areaCode: '996'}).convert();
// +996 (800) 271-8281

```


## API

### format

Format the number to local, domestic, international, or a custom type

```js
let number = new phoneNumberFormatter('18001234567');
number.format({type: 'international', areaCode: '996', separator: '.', letters: true});
// +996.(800).123.4567
```

### convert

Convert any letters to numbers

```js
let number = new phoneNumberFormatter('123WHAT');
number.convert();
// 1239428
```

### toString

Get phone number as a string


### addType

Add new type to be used in format method

```js
// The X's signify numbers and the Y's signify the area code by default
phoneNumberFormatter.addType('china', '0 +YYY XXX-XXX');
number = new phoneNumberFormatter('314159').format({type: 'china', areaCode: '591'});
// 0 +591 314-159

// Different letters or symbols can be used as delimiters
phoneNumberFormatter.addType('x-ray', '(VVV) WWW-XRAY', {number: 'W', areaCode: 'V'});
number = new phoneNumberFormatter('314159').format({type: 'x-ray'});
// (314) 159-XRAY
```

### getType

Gets the key for any default or custom type

```js
phoneNumberFormatter.getType('china');
// 0 +YYY XXX-XXX
```

## Examples

See [test.js](https://github.com/drewthoennes/phone-number-formats/blob/master/test.js) for examples

## License

[MIT](https://github.com/drewthoennes/phone-number-formats/blob/master/license)
