# Regex Tutorial: Enforce That Email Structure!

In web development, validating user input is a crucial task, especially when it comes to ensuring that email addresses are in the correct format. One way to achieve this is through the use of regular expressions, or regex. This tutorial will break down the components of a regex pattern that matches email addresses, explaining how each part contributes to identifying a valid email address.

## Summary

The regex we'll be discussing is used to match a standard email address format:

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

This pattern ensures that the email has a valid format, such as example@domain.com. We'll break down each component of this regex to understand how it works.

## Table of Contents

- [Anchors: ^ and $](#anchors--and-)
- [User Name Segment: ([a-z0-9_.-]+)](#user-name-segment-a-z0-9_-)
- [The @ Symbol](#the--symbol)
- [Domain Name Segment: ([\da-z.-]+)](#domain-name-segment-da-z-)
- [Top-Level Domain: ([a-z.]{2,6})](#top-level-domain-a-z26)
- [Valid and Invalid Email Examples](#valid-and-invalid-email-examples)
- [References](#references)
- [About the Author](#author)

## Regex Components

### Anchors: `^ and $ `

The ^ and $ symbols are anchors in regex that mark the start and end of the string, respectively. They ensure that the regex pattern matches the entire string, not just a part of it.

* `^` asserts the position at the start of the string.
* `$` asserts the position at the end of the string.

### User Name Segment: `([a-z0-9_.-]+)`

This part of the regex matches the user name part of the email, which comes before the @ symbol.

* `[a-z0-9_\.-]` matches any lowercase letter, digit, underscore (`_`), period (`.`), or hyphen (`-`).
* `+` ensures that this part of the email has one or more characters.

#### Examples:

* `user_name123` (matches)
* `user@domain.com` (does not match)

### The `@` Symbol

The `@` symbol is a fixed part of the email format. The regex matches this symbol directly, ensuring it appears between the user name and domain name.

#### Example:

* `example@domain.com` (matches)
* `exampleAtdomain.com` (does not match)

### Domain Name Segment: `([\da-z.-]+)`

This segment matches the domain name part of the email, which comes after the @ symbol and before the top-level domain.

* `[\da-z\.-]` matches any digit (`\d`), lowercase letter, period (`.`), or hyphen (`-`).
* `+` ensures that this part of the email has one or more characters.

#### Examples:

* `domain-name` (matches)
* `domain..com` (does not match)

### Top-Level Domain: `([a-z.]{2,6})`

The top-level domain (TLD) is the final part of the email, such as .com or .org.

* `[a-z\.]` matches any lowercase letter or period.
* `{2,6}` specifies that the TLD must be between 2 and 6 characters long.

#### Examples:

* `.com` (matches)
* `.museum` (matches)
* `.a` (does not match)

### Valid and Invalid Email Examples
Valid Emails:

* `test@example.com`
* `user.name@domain.co`

Invalid Emails:

* `user@domain..com` (multiple periods in domain)
* `user@.com` (missing domain name)

## References

* [Regex Tutorial - MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions)
* [Regular Expressions 101](https://regex101.com/)

## Author

Hello! I am Alexis Langille, the author of this tutorial. 

Please check out more of my projects on [GitHub](https://github.com/alangille01)