---
title: GST calculator
---

# Problem Statement

Given initial price and GST rates of different items, calculate final price after adding gst and return it after rounding off upto 2 digits.

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
final_price(100, 'milk') # return 128.00
final_price(102, 'labelled_curd') # return 102.51
is_two_digit_even(220 ,'unlabelled_curd') # return 220.00
```

# Solution

```py3 test.py -r 'python test.py'
<prefix>
# some prefix   
</prefix>
<template>
def final_price(price: int, category: str) -> float:
    '''
    Given initial price and GST rates, return final price after adding gst.
    Round it off upto 2 digits.

    Arguments:
    price: int - price of item.
    category: str - category of item (milk, mobile, laptop, etc)

    Return: float - final sales price after tax
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
is_equal(final_price(100, 'unlabeled_curd'), 100.0)
```

## Output 2

```
100.0
```

## Input 3

```
is_equal(final_price(100, 'labelled_curd'), 105.0)
```

## Output 3

```
105.0
```

## Input 4

```
is_equal(final_price(100, 'ghee'), 112.0)
```

## Output 4

```
112.0
```

## Input 5

```
is_equal(final_price(100, 'butter'), 112.0)
```

## Output 5

```
112.0
```

## Input 6

```
is_equal(final_price(100, 'cheese'), 112.0)
```

## Output 6

```
112.0
```

## Input 7

```
is_equal(final_price(100, 'laptop'), 118.0)
```

## Output 7

```
118.0
```

## Input 8

```
is_equal(final_price(100, 'mobile'), 118.0)
```

## Output 8

```
118.0
```

## Input 9

```
is_equal(final_price(100, 'custard_powder'), 128.0)
```

## Output 9

```
128.0
```

## Input 10

```
is_equal(final_price(100, 'cocoa_powder'), 128.0)
```

## Output 10

```
128.0
```

## Input 11

```
is_equal(final_price(100, 'chewing_gum'), 128.0)
```

## Output 11

```
128.0
```

## Input 12

```
is_equal(final_price(100, 'churan_for_pan'), 128.0)
```

## Output 12

```
128.0
```
