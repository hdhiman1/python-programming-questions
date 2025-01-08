---
title: GST calculator
---

# Problem Statement

Given initial price `price` and GST rate `gst`, return final price after adding gst rounded off upto 2 digits.

**Example**
```py3
final_price(100, 28) # return 128.00
final_price(102, 5) # return 102.51
is_two_digit_even(220 ,0) # return 220.00
```

# Solution

```py3 test.py -r 'python test.py'
<prefix>
# some prefix   
</prefix>
<template>
def final_price(price: int, gst: int) -> float:
    '''
    Given initial price and GST rate, return final price after adding gst.
    Round it off upto 2 digits.

    Arguments:
    price: int - price of item.
    gst: int - gst rate in percent

    Return: int - final sales price after tax
    '''
    <los>...</los>
    <sol>return round(price + price*(gst/100), 2)</sol>
    test = <los>...</los><sol>'test'</sol> #tests
</template>
<suffix>
# some suffix
</suffix>
<suffix_invisible>
{% include '../function_type_and_modify_check_suffix.py.jinja' %}
</suffix_invisible>
```

# Public Test Cases

## Input 1

```
is_equal(final_price(100, 28), 128.0)
```

## Output 1

```
128.0
```

## Input 2

```
is_equal(final_price(102,0), 102.0)
```

## Output 2

```
102.0
```

## Input 3 

```
is_equal(final_price(100, 5), 105.0)
```

## Output 3

```
105.0
```

# Private Test Cases

## Input 1

```
is_equal(final_price(100, 12), 112.0)
```

## Output 1

```
112.0
```