
# @moebius/ng-validators

[![npm version](https://badge.fury.io/js/%40moebius%2Fng-validators.svg)](https://badge.fury.io/js/%40moebius%2Fng-validators)

This repository contains a collection of useful Angular input validators,
some of which could also be used independently.


## Installation

`npm i -S @moebius/ng-validators`


## Usage

```typescript
import { birthDateValidator } from '@moebius/ng-validators';

this.form = this.formBuilder.group({
  birthDate: [null, [
    birthDateValidator({
      minYearsOld: 18,
      maxYearsOld: 60,
    }),
  ]],
});
```


## Provided validators

### Password

`passwordValidator(options: PasswordValidatorOptions)`

Checks if value is a correct password.

* `options.minLength: number`
* `options.maxLength: number`
* `options.requireLetters: boolean`
* `options.requireLowerCaseLetters: boolean`
* `options.requireUpperCaseLetters: boolean`
* `options.requireNumbers: boolean`
* `options.requireSpecialCharacters: boolean`


### Match Other

`matchOtherValidator(otherControlName: string)`

Checks if value equals to the value in another input.
Also, watched for events from another input to re-validate when necessary.

* `otherControlName: string` — specify the name of another form control,
  both controls must be in the same control group


### Skype Name

`skypeNameValidator()`

Checks if value contains valid skype login name.


### Birth Date

`birthDateValidator(options: BirthDateValidatorOptions)`

Validates the specified date of birth relative to the current date.

The date could be specified as native Date object, moment.js object
or js-joda LocalDate.

* `options.minYearsOld: number` — minimal years old, e.g. `18` (legal age)
* `options.maxYearsOld: number` — maximum years old, e.g. `60` (pension age)


## Support

If this library is useful to you, please add a star on [GitHub repository][repo-gh].

Thank you!


## License

The MIT License (MIT)

Copyright (c) 2017—2019, MOEBIUS FOUNDATION, Slava Fomin II

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.


  [repo-gh]: https://github.com/moebius-mlm/ng-validators
  [js-joda]: https://js-joda.github.io/js-joda/index.html
