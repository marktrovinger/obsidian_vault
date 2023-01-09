# Basic Text Processing
Created: 2023-01-09 17:22

## RegEx
RegExs are a formal language for specifying text string, with a specific format. Disjunctions are any letters inside of square brackets, with ranges as well.
### Example
`[wW]oodchuck` would match either case of the word

To negate a disjunction, we would use the carat character.
### Example
`[^A-Z]` would be no uppercase letters

The pipe operator `|` can be used for disjunction. It serves as an or operator.

Look over what the operators do for regex (? * +).

## Anchors
Anchors are characters that prefix or suffix strings, `^` for the beginning, and `$` for the end of a string.

## References
1. 