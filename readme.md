# Phone Number Formatter

Easy way to format and convert phone numbers **now with method chaining**

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

Format the number to local, domestic, or international

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

## License

[MIT](https://github.com/drewthoennes/phone-number-formats/blob/master/license)
