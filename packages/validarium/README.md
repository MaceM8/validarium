<p align="center">
  <a href="https://validarium.js.org">
    <img alt="Validarium" src="https://validarium.js.org/_media/logo.png" width="300" />
  </a>
</p>

<h1 align="center">
  <a href="https://lundegaard.eu">
    <img alt="by Lundegaard" src="https://validarium.js.org/_media/by-lundegaard.png" width="120" />
  </a>
</h1>

<h3 align="center">
🖍️ 🛡  🚀
</h3>

<h3 align="center">
Validations done right.
</h3>

<p align="center">
Platform-agnostic validation library for JavaScript applications with extra focus on composable validations and message translations. Includes (pretty much) out-of-the-box support for both <a href="https://redux-form.com/">Redux Form</a> and <a href="https://github.com/formatjs/react-intl">React Intl</a>.
</p>

<p align="center">
Create your validation schema based on priciples of functional programming.
</p>

<p align="center">
<a href="https://runkit.com/aizerin/validarium">Open Validarium in a RunKit sandbox!</a>
</p>

<p align="center">
<a href="https://validarium.js.org">See our documentation site.</a>
</p>

<p align="center">
  <a href="https://github.com/lundegaard/validarium">
    <img src="https://flat.badgen.net/badge/-/github?icon=github&label" alt="Github" />
  </a>

  <img src="https://flat.badgen.net/badge/license/MIT/blue" alt="MIT License" />

  <a href="https://travis-ci.org/lundegaard/validarium">
    <img src="https://img.shields.io/travis/lundegaard/validarium/master.svg?style=flat-square" alt="Travis" />
  </a>

  <a href="https://npmjs.com/package/validarium">
    <img src="https://img.shields.io/npm/dm/@validarium/core.svg" alt="Downloads" />
  </a>

  <a href="https://npmjs.com/package/validarium">
    <img src="https://flat.badgen.net/npm/v/validarium" alt="Version" />
  </a>
</p>

```js
import { validate, isRequired, isEmail, hasLengthMax, hasValueMin } from 'validarium';

const validateUserForm = validate({
	email: [isRequired, isEmail, hasLengthMax(200)],
	age: [isRequired, isNumber, hasValueMin(18)],
});

validateUserForm({ email: 'something', age: 16 });
// Returns { email: EmailMessage, age: NumberMessage }
//
// EmailMessage is { id: 'validarium.isEmail', defaultMessage: 'Not a valid email format' }
// NumberMessage is { id: 'validarium.isNumber', defaultMessage: 'Not a number' }
```

Every validation is optional and null-safe. If you want to test against `null`, please use the `isRequired` validation.

Of course, validating field arrays, combining multiple validation schemas, and overriding validation messages with custom ones is supported as well.

## Installation

Use either of these commands based on the package manager you prefer.

```sh
yarn add validarium
```

```sh
npm i validarium
```
### CDN

It is possible to use `validarium` to start quickly prototype directly in browser. 

We provide two Universal Module Definition (UMD) bundles:

- development version: [https://unpkg.com/validarium@latest/dist/validarium.js](https://unpkg.com/validarium@latest/dist/validarium.js)
- production version: [https://unpkg.com/validarium@latest/dist/validarium.min.js](https://unpkg.com/validarium@latest/dist/validarium.js)

⚠️ Using this approach in production is discouraged though - the client has to download the entire library, regardless of which functions are actually used, affecting performance and bandwidth utilization.

## Related projects

- [@redux-tools](https://github.com/lundegaard/redux-tools) – Maintaining large Redux applications with ease.
- [react-union](https://github.com/lundegaard/react-union) – Integrate React apps into various CMSs seamlessly.
- [lundium](https://github.com/lundegaard/lundium) – Beautiful React component library.

## Contributing

We are open to all ideas and suggestions, feel free to open an issue or a pull request!

See the [contribution guide](contributing) for guidelines.

## Related projects

- [@redux-tools](https://github.com/lundegaard/redux-tools) – Maintaining large Redux applications with ease.
- [react-union](https://github.com/lundegaard/react-union) – Integrate React apps into various CMSs seamlessly.
- [lundium](https://github.com/lundegaard/lundium) – Beautiful React component library.

## License

All packages are distributed under the MIT license. See the license [here](https://github.com/lundegaard/validarium/blob/master/LICENSE).
