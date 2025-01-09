---
title: GST calculator
---

# Problem Statement

Given initial price `price` and GST rate `gst`, return final price after adding gst rounded off upto 2 digits.

GST Rate on

milk : 0%
unlabeled_curd : 0%
labelled_curd : 5%
ghee : 12%
butter : 12%
cheese : 12%
laptop : 18%
mobile : 18%
custard_powder	: 28%
cocoa_powder : 28%
chewing_gum : 28%
churan_for_pan : 28%


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
def final_price(price: int, category: str) -> float:
    '''
    Given initial price and GST rate, return final price after adding gst.
    Round it off upto 2 digits.

    Arguments:
    price: int - price of item.
    gst: int - gst rate in percent

    Return: int - final sales price after tax
    '''
    <los>...</los>
    <sol>
    
    if category == 'milk' or category == 'unlabeled_curd':
        gst = 0
    elif category == 'ghee' or category == 'butter' or category == 'cheese':
        gst = 12
    elif category == 'laptop' or category == 'mobile':
        gst = 18
    elif category == 'custard_powder' or category == 'cocoa_powder' or category == 'chewing_gum' or category == 'churan_for_pan':
        gst = 28
    elif category == 'labelled_curd':
        gst = 5
    final_price =  price + price*(gst/100)
    return round(final_price, 2)
    
    </sol>
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
is_equal(final_price(100, 'milk'), 100.0)
```

## Output 1

```
100.0
```

## Input 2

```
is_equal(final_price(610, 'ghee'), 683.2)
```

## Output 2

```
683.2
```

## Input 3 

```
is_equal(final_price(50000, 'mobile'), 59000.0)
```

## Output 3

```
59000.0
```


# Private Test Cases

## Input 1

```
is_equal(final_price(100, 'milk'), 100.0)
```

## Output 1

```
100.0
```
## Input 2

```
is_equal(final_price(100, 'mobile'), 118.0)
```

## Output 2

```
118.0
```
