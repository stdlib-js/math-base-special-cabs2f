<!--

@license Apache-2.0

Copyright (c) 2021 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->

# cabs2f

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Compute the squared [absolute value][absolute-value] of a single-precision [complex][@stdlib/complex/float32] floating-point number.

<section class="intro">

The [absolute value][absolute-value] of a [complex][@stdlib/complex/float32] number is defined as

<!-- <equation class="equation" label="eq:absolute_value_complex" align="center" raw="|a + bi| = \sqrt{a^2 + b^2}" alt="Absolute value"> -->

<div class="equation" align="center" data-raw-text="|a + bi| = \sqrt{a^2 + b^2}" data-equation="eq:absolute_value_complex">
    <img src="https://cdn.jsdelivr.net/gh/stdlib-js/stdlib@6b7ea3a67c5943feb168cbe1336ba977959acf9a/lib/node_modules/@stdlib/math/base/special/cabs2f/docs/img/equation_absolute_value_complex.svg" alt="Absolute value">
    <br>
</div>

<!-- </equation> -->

which corresponds to the length of a vector from the origin to a complex value plotted in the complex plane.

</section>

<!-- /.intro -->

<section class="installation">

## Installation

```bash
npm install @stdlib/math-base-special-cabs2f
```

Alternatively,

-   To load the package in a website via a `script` tag without installation and bundlers, use the [ES Module][es-module] available on the [`esm` branch][esm-url].
-   If you are using Deno, visit the [`deno` branch][deno-url].
-   For use in Observable, or in browser/node environments, use the [Universal Module Definition (UMD)][umd] build available on the [`umd` branch][umd-url].

The [branches.md][branches-url] file summarizes the available branches and displays a diagram illustrating their relationships.

</section>

<section class="usage">

## Usage

```javascript
var cabs2f = require( '@stdlib/math-base-special-cabs2f' );
```

#### cabs2f( z )

Computes the squared [absolute value][absolute-value] of a single-precision [complex][@stdlib/complex/float32] floating-point number.

```javascript
var Complex64 = require( '@stdlib/complex-float32' );

var y = cabs2f( new Complex64( 5.0, 3.0 ) );
// returns 34.0
```

</section>

<!-- /.usage -->

<section class="notes">

## Notes

-   Be careful to avoid overflow and underflow.
-   Depending on the environment, this function _may_ have better performance than computing the [absolute value][absolute-value] of a [complex][@stdlib/complex/float32] number and then squaring. Hence, where appropriate, consider using `cabs2f()` over [`cabsf()`][@stdlib/math/base/special/cabsf].

</section>

<!-- /.notes -->

<section class="examples">

## Examples

<!-- eslint-disable max-len -->

<!-- eslint no-undef: "error" -->

```javascript
var Complex64 = require( '@stdlib/complex-float32' );
var discreteUniform = require( '@stdlib/random-base-discrete-uniform' ).factory;
var cabs2f = require( '@stdlib/math-base-special-cabs2f' );

// Create a PRNG to generate uniformly distributed pseudorandom integers:
var rand = discreteUniform( -50, 50 );

// Compute the squared absolute value for a set of random numbers...
var z;
var i;
for ( i = 0; i < 100; i++ ) {
    z = new Complex64( rand(), rand() );
    console.log( 'cabs2f(%s) = %d', z.toString(), cabs2f( z ) );
}
```

</section>

<!-- /.examples -->

<!-- C interface documentation. -->

* * *

<section class="c">

## C APIs

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- C usage documentation. -->

<section class="usage">

### Usage

```c
#include "stdlib/math/base/special/cabs2f.h"
```

#### stdlib_base_cabs2f( z )

Computes the squared [absolute value][absolute-value] of a single-precision complex floating-point number.

```c
#include <complex.h>

float y = stdlib_base_cabs2f( 5.0+3.0*I );
// returns 34.0f
```

The function accepts the following arguments:

-   **z**: `[in] float complex` input value.

```c
float stdlib_base_cabs2f( const float complex z );
```

</section>

<!-- /.usage -->

<!-- C API usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

</section>

<!-- /.notes -->

<!-- C API usage examples. -->

<section class="examples">

### Examples

```c
#include "stdlib/math/base/special/cabs2f.h"
#include <stdio.h>
#include <complex.h>

int main() {
    float complex x[] = { 3.14f+1.0f*I, -3.14f-1.0f*I, 0.0f+0.0f*I, 0.0f/0.0f+0.0f/0.0f*I };

    float complex v;
    float y;
    int i;
    for ( i = 0; i < 4; i++ ) {
        v = x[ i ];
        y = stdlib_base_cabs2f( v );
        printf( "f(%f + %f) = %f\n", crealf( v ), cimagf( v ), y );
    }
}
```

</section>

<!-- /.examples -->

</section>

<!-- /.c -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2022. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/math-base-special-cabs2f.svg
[npm-url]: https://npmjs.org/package/@stdlib/math-base-special-cabs2f

[test-image]: https://github.com/stdlib-js/math-base-special-cabs2f/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/math-base-special-cabs2f/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/math-base-special-cabs2f/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/math-base-special-cabs2f?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/math-base-special-cabs2f.svg
[dependencies-url]: https://david-dm.org/stdlib-js/math-base-special-cabs2f/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://gitter.im/stdlib-js/stdlib/

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/math-base-special-cabs2f/tree/deno
[umd-url]: https://github.com/stdlib-js/math-base-special-cabs2f/tree/umd
[esm-url]: https://github.com/stdlib-js/math-base-special-cabs2f/tree/esm
[branches-url]: https://github.com/stdlib-js/math-base-special-cabs2f/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/math-base-special-cabs2f/main/LICENSE

[absolute-value]: https://en.wikipedia.org/wiki/Absolute_value

[@stdlib/math/base/special/cabsf]: https://github.com/stdlib-js/math-base-special-cabsf

[@stdlib/complex/float32]: https://github.com/stdlib-js/complex-float32

</section>

<!-- /.links -->
