Password Strength Checker
=========================

This vue component provides a customized password field linked to the zxcvbn password strength checker. it evaluates, in real-time, the strength if the password being entered and displays a strength meter to guide the user to a good password.

## Installation

This is a single file component so can be integrated into your project in a number of ways, e.g. Webpack + vue-loader or Browserify + vueify, however it it written in pure html, javascript and css so doesn't require an pre-processors. More information about single file components can be found on the [Vuejs website](http://vuejs.org/guide/application.html#Single-File-Components).

It depends on the [zxcvbn library](https://blogs.dropbox.com/tech/2012/04/zxcvbn-realistic-password-strength-estimation) which will need to be loaded on the page where the field will be placed. That library is a large, and its author has some [recommendations](https://github.com/dropbox/zxcvbn/blob/master/README.md) on how it may be loaded, but as the password field is typically not used until a few seconds after a user lands on the relevant page, it's normally OK to just load it asynchronously at the very end of the page.

## Usage

TBD

## License

This package is licensed under the [MIT license](http://opensource.org/licenses/MIT).
