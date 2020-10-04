# About

`utopian-sass` is a Sass module adaption of [Utopia](https://utopia.fyi/) for fluid responsive design. It is recommended you read about the generator [here](https://utopia.fyi/generator-mk-ii) if you haven't already.

## Getting Started

First thing to do is to install the package:

```
npm install utopian-sass
```

Then in your Sass, load the module like so:

```scss
@use '../node_modules/utopian-sass/utopian.scss';
```

This will generate fluid responsive CSS properties according to the default settings of the module.

## Configuration

`utopian-sass` uses configurable default values in its generation, which correspond to the options available in the [generator](https://utopia.fyi/generator-mk-ii), as well as options for prefixing the generated CSS properties. They appear in the codebase as follows:

```scss
$min-width: 320 !default;
$min-size: 21 !default;
$min-scale: 1.2 !default;

$max-width: 1140 !default;
$max-size: 24 !default;
$max-scale: 1.25 !default;

$neg-steps: 2 !default;
$pos-steps: 5 !default;

$prefix: 'fluid' !default;
$step-prefix: 'step' !default;
```

Any of these values can be configured when loading the module with the `@use` rule, for example:

```scss
@use '../node_modules/utopian-sass/utopian.scss' with (
  $pos-steps: 7,
  $min-size: 18,
  $max-size: 22
);
```

**NB:** Ensure that when providing values for variables that contain numbers, you provide numbers that are _unitless_. Doing otherwise will likely lead to generated CSS properties that have no affect, and currently the module will not warn you if configured incorrectly.
