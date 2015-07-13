# Responsive Table

After looking at some [good](http://codyhouse.co/demo/pricing-tables/)
[examples](https://css-tricks.com/responsive-data-tables/) of responsive
tables around the web, I decided to share my take on them.
__Check out the [demo](https://gnclmorais.github.io/responsive-table-example)__!

This repo was built from the ground up, stripping all the eye candy CSS to a
separate file and keeping the bare essential CSS to bestow responsiveness into
a table into a different file.

## Basic technique

The technique in play here has a few simple steps:
- Wrap the “table” in `.smart-table`
- Emulate visual columns & rows with `.smart-table--column` and
  `.smart-table--row`
- `.smart-table--column__collapsable` is added to columns that we want to be
  hidden in smaller screens (usually the left column, where we have the name
  or meaning of each row).
- In each “row”, this row name/meaning is duplicated at its start, wrapped
  in `.smart-table--row-meaning`
- Each “row” (or cell) should have a `.smart-table--row-meaning` element (with
  the name/meaning of the row) and a `.smart-table--row-value` (where the
  actual value of that cell will be).
- By default (_mobile first_ approach), `.smart-table--column__collapsable`
  will be hidden and `.smart-table--row-meaning` will be visible.
- When horizontal space starts getting scarce (use the meadia query most
  relevant to your case), `.smart-table--row-meaning` will be hidden and
  `.smart-table--column__collapsable` will be visible.

## Abstract structure
```
.smart-table
  .smart-table--column[.smart-table--column__collapsable]
    .smart-table--row[.smart-table--row-header.smart-table--row-header__hidden]
    .smart-table--row[.smart-table--row-meaning]
    …
  .smart-table--column
    .smart-table--row[.smart-table--row-header]
    .smart-table--row
      .smart-table--row-meaning
      .smart-table--row-value
    …
  .smart-table--column
    …
```

## Credits
- The [responsive table technique](http://codyhouse.co/demo/pricing-tables/)
  that I used as a base to my interpretation.
- This demo was easily built thanks to some flexbox goodness.
  [This](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) is still
  my favourite place to go to, when in doubt.
