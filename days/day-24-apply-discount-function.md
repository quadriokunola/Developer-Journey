# Day 24: Build an Apply Discount Function (Lab)

Date: 2026-08-05
Topic: Functions and conditionals — validating inputs and calculating a percentage discount

## What I did
Completed the "Build an Apply Discount Function" lab (all 11 tests passing). Defined `apply_discount(price, discount)` using a chain of `if`/`elif`/`else` checks: validated that `price` and `discount` are numeric types with `isinstance(x, (int, float))`, validated that `price > 0` and that `discount` falls between 0 and 100, then calculated `discount_result = price * discount / 100` and returned `price - discount_result`.

## What clicked
Using `isinstance()` to check a value against multiple types in one call (e.g. `isinstance(price, (int, float))`) — once the hint pointed me back to it, it clicked as the right tool for "is this a number or not" validation.

## What was confusing
Two friction points: first, I initially reached for `!=` instead of `isinstance()` for the type check, having forgotten `isinstance()` was available, and needed a hint to get there. Second, I blanked on the formula for calculating a percentage discount and had to check freeCodeCamp's help section to recall the math. Also noted I need to get better at reading back through my own code to catch small mistakes before running it.

## Tomorrow
Rely less on hints and push through problems by reasoning them out first, asking for help only when genuinely stuck. Next up per the roadmap: Build a Caesar Cipher (Workshop).

## Code

![Apply Discount Function - passing tests](images/day-24-apply-discount-code.png)

```python
def apply_discount(price,discount):
    if not isinstance(price, (int,float)):
        return("The price should be a number")

    elif not isinstance(discount, (int, float)):
        return("The discount should be a number")

    elif price <= 0 :
        return("The price should be greater than 0")

    elif discount < 0 or discount > 100:
        return("The discount should be between 0 and 100")

    else:
        discount_result = price * discount/100
        final_price = price - discount_result
        return final_price
```
