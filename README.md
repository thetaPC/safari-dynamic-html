# Safari Dynamic HTML bug

## Description

Safari does not update when changing the HTML through Javascript. It uses the old HTML to determine the direction of the element. This is a problem when using `:dir()` to apply different styles to RTL and LTR languages.

## Steps to reproduce

1. Set the `dir` attribute of the `html` element to `ltr` in the HTML file.
2. Create a script that changes the `dir` attribute of the `html` element to `rtl` when the page is loaded.
3. Create a CSS file that applies different styles to an element based on the `dir` attribute.
4. Open the HTML file in Safari.

## Expected behavior

The element should be styled according to the `dir` attribute of the `html` element regardless of the initial value.

## Actual behavior

The element is styled according to the initial value of the `dir` attribute of the `html` element.

## Other information

This works as expected in Chrome and Firefox. The bug is present in Safari 16.4+. I have not tested older versions.

## Webkit bug report

[Bug 257133](https://bugs.webkit.org/show_bug.cgi?id=257133)
