aldeed:autoform-bs-datepicker
=========================

An add-on Meteor package for [aldeed:autoform](https://github.com/aldeed/meteor-autoform). Provides a single custom input type, "bootstrap-datepicker", which renders an input using the [bootstrap-datepicker](http://bootstrap-datepicker.readthedocs.org/en/release/index.html) plugin.

## Prerequisites

Bootstrap and the plugin library must be installed separately.

In a Meteor app directory, enter:

```
$ meteor add mizzao:bootstrap-3
$ meteor add rajit:bootstrap3-datepicker
$ meteor add aldeed:autoform@4.0.0-rc9
```

## Installation

In a Meteor app directory, enter:

```
$ meteor add aldeed:autoform-bs-datepicker
```

## Usage

Specify "bootstrap-datepicker" for the `type` attribute of any input. This can be done in a number of ways:

In the schema, which will then work with a `quickForm` or `afQuickFields`:

```js
{
  date: {
    type: Date,
    autoform: {
      type: "bootstrap-datepicker"
    }
  }
}
```

Or on the `afFieldInput` component or any component that passes along attributes to `afFieldInput`:

```js
{{> afQuickField name="typeTest" type="bootstrap-datepicker"}}

{{> afFormGroup name="typeTest" type="bootstrap-datepicker"}}

{{> afFieldInput name="typeTest" type="bootstrap-datepicker"}}
```

This input type is intended to be used with `type: Date` schema keys, but it also works with other schema types. Here's a list:

* `Date`: Value is stored as a `Date` object representing midnight in the UTC timezone on the morning of the selected date.
* `String`: Value is stored as a string representation of the selected date in ISO format, e.g., "2014-11-25".
* `Number`: Value is stored as the result of calling `getTime()` on the `Date` object (representing midnight in the UTC timezone on the morning of the selected date).
* `Array`: If the schema expects an array of `Date` or `String` or `Number`, the value is converted to a one-item array and stored.

To provide bootstrap-datepicker options, set a `datePickerOptions` attribute equal to a helper that returns the options object. Most of the `data-date` attributes that the plugin recognizes should also work.

## Demo

[Live](http://autoform.meteor.com/types)

## Contributing

Anyone is welcome to contribute. Fork, make your changes, and then submit a pull request.

[![Support via Gittip](https://rawgithub.com/twolfson/gittip-badge/0.2.0/dist/gittip.png)](https://www.gittip.com/aldeed/)
