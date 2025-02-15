# Unexpected Behavior of `calc()` with Percentage and Pixel Subtraction

This repository demonstrates a subtle bug related to the CSS `calc()` function when combining percentage and pixel values with subtraction.  The issue manifests when the resulting calculated width becomes negative, leading to unpredictable layout behavior.  The bug is particularly difficult to debug because it is dependent on the context in which the element is used.

**Problem:**

The CSS code attempts to set the width of an element to 50% of its parent's width minus 10 pixels. If the parent's width is less than 20 pixels, the calculation results in a negative value, causing unexpected rendering problems.  Browsers handle negative widths differently, some ignoring it and setting the width to 0 and others may raise warnings.

**Solution:**

The provided solution introduces a `min()` function within the `calc()` function to ensure that the width never falls below zero. This resolves the issue and makes the layout more robust.  This solution makes the layout much more robust and predictable.