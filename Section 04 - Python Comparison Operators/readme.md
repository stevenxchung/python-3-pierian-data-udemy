# Section 4 Notes

This section covers comparison operators in python.

## Python Comparison Operators

Operator | Description
--- | --- | ---
== | If the values of two operands are equal, then the condition becomes true
!= | If values of two operands are not equal, then condition becomes true
> | If the value of left operand is greater than the value of right operand, then condition becomes true
< | If the value of left operand is less than the value of right operand, then condition becomes true
>= | If the value of left operand is greater than or equal to the value of right operand, then condition becomes true
<= | If the value of left operand is less than or equal to the value of right operand, then condition becomes true

# Chaining Comparison Operators

There are several keywords used to chain comparison operators:
* When using the *and* keyword, both statements have to be true.
* When using the *or* keyword, either statements can be true

Additionally, we have a *not* keyword which returns the opposite of the expected result:

```python
not 1 == 1 # Since this is normally True, the not keyword will return False
```
