---
title: Top spenders
---

# Problem Statement

Write a function get_top_spenders(transactions, n) that takes the dataset and a number n as input and returns the top n customers by total spending.

sample transactions:

transactions = [
    {"transaction_id": 11, "customer_id": 1, "amount": 25000.0, "category": "Electronics"},
    {"transaction_id": 12, "customer_id": 2, "amount": 800.0, "category": "Groceries"},
    {"transaction_id": 13, "customer_id": 1, "amount": 1200.0, "category": "Electronics"},
    {"transaction_id": 14, "customer_id": 3, "amount": 450.0, "category": "Books"},
    {"transaction_id": 15, "customer_id": 2, "amount": 150.0, "category": "Groceries"},
    {"transaction_id": 16, "customer_id": 4, "amount": 450.0, "category": "Electronics"},
    {"transaction_id": 17, "customer_id": 1, "amount": 260.0, "category": "Books"},
    {"transaction_id": 18, "customer_id": 3, "amount": 700.0, "category": "Clothing"},
    {"transaction_id": 19, "customer_id": 4, "amount": 3000.0, "category": "Electronics"},
    {"transaction_id": 20, "customer_id": 5, "amount": 100.0, "category": "Groceries"},
]


**Example**
```py3
get_top_spenders(transactions, 2) # [(1, 26460.0), (4, 3450.0)]
get_top_spenders(transactions, 3) # [(1, 26460.0), (4, 3450.0), (3, 1150.0)]
get_top_spenders(transactions, 4) # [(1, 26460.0), (4, 3450.0), (3, 1150.0), (2, 950.0)]
```

# Solution

```py3 test.py -r 'python test.py'
<prefix>
# some prefix   
</prefix>
<template>
def get_top_spenders(transactions: list, n: int) -> list:
    '''
    Write a function get_top_spenders(transactions, n) that takes the dataset and a number n as input and returns a list of tuples, the top n customers by total spending.

    Arguments:
    transactions: list
    n: no. of tuples (customers) in the list of top spenders that the function will return

    Return: a list in the form [(customer1, total_spending_of_customer1),(customer2, total_spending_of customer_2)...]
    '''
    
    <los>...</los>
    <sol>
    customer_spending = {}
    for transaction in transactions:
        customer_id = transaction["customer_id"]
        amount = transaction["amount"]
        if customer_id in customer_spending:
            customer_spending[customer_id] += amount
        else:
            customer_spending[customer_id] = amount

    sorted_spenders = sorted(customer_spending.items(), key=lambda x: x[1], reverse=True)

    return sorted_spenders[:n]
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
transactions = [
    {"transaction_id": 21, "customer_id": 1, "amount": 35000.0, "category": "Furniture"},
    {"transaction_id": 22, "customer_id": 5, "amount": 120.0, "category": "Stationary"},
    {"transaction_id": 23, "customer_id": 7, "amount": 1400.0, "category": "Electronics"},
    {"transaction_id": 24, "customer_id": 2, "amount": 450.0, "category": "Books"},
    {"transaction_id": 25, "customer_id": 8, "amount": 140.0, "category": "Groceries"},
    {"transaction_id": 26, "customer_id": 2, "amount": 440.0, "category": "Tools"},
    {"transaction_id": 27, "customer_id": 2, "amount": 260.0, "category": "Books"},
    {"transaction_id": 28, "customer_id": 7, "amount": 110.0, "category": "Toys"}
]

is_equal(
    get_top_spenders(transactions, 5),
    [(1, 35000.0), (7, 1510.0), (2, 1150.0), (8, 140.0), (5, 120.0)]
)
```

## Output 1

```
[(1, 35000.0), (7, 1510.0), (2, 1150.0), (8, 140.0), (5, 120.0)]
```

## Input 2

```
transactions = [
    {"transaction_id": 31, "customer_id": 5, "amount": 22000.0, "category": "Electronics"},
    {"transaction_id": 32, "customer_id": 7, "amount": 800.0, "category": "Cosmetics"},
    {"transaction_id": 34, "customer_id": 9, "amount": 750.0, "category": "Home improvement"},
    {"transaction_id": 35, "customer_id": 12, "amount": 415.0, "category": "Groceries"},
    {"transaction_id": 36, "customer_id": 11, "amount": 450.0, "category": "Electronics"},
    {"transaction_id": 37, "customer_id": 12, "amount": 600.0, "category": "Kids"},
    {"transaction_id": 38, "customer_id": 5, "amount": 700.0, "category": "Clothing"},
    {"transaction_id": 40, "customer_id": 12, "amount": 50.0, "category": "Kitchenware"}
]

is_equal(
    get_top_spenders(transactions, 3),
    [(5, 22700.0), (12, 1065.0), (7, 800.0)]
)
```

## Output 2

```
[(5, 22700.0), (12, 1065.0), (7, 800.0)]
```

## Input 3 

```
transactions = [
    {"transaction_id": 41, "customer_id": 10, "amount": 5000.0, "category": "Power tools"},
    {"transaction_id": 43, "customer_id": 4, "amount": 1200.0, "category": "Furniture"},
    {"transaction_id": 45, "customer_id": 11, "amount": 150.0, "category": "Daily essentials"},
    {"transaction_id": 46, "customer_id": 12, "amount": 40.0, "category": "Health and Wellness"},
    {"transaction_id": 50, "customer_id": 10, "amount": 100.0, "category": "Groceries"},
]

is_equal(
    get_top_spenders(transactions, 4),
    [(10, 5100.0), (4, 1200.0), (11, 150.0), (12, 40.0)]
)
```

## Output 3

```
[(10, 5100.0), (4, 1200.0), (11, 150.0), (12, 40.0)]
```

# Private Test Cases

## Input 1

```
transactions = [
    {"transaction_id": 51, "customer_id": 15, "amount": 74999.0, "category": "Mobiles"},
    {"transaction_id": 52, "customer_id": 21, "amount": 110.0, "category": "Groceries"},
    {"transaction_id": 53, "customer_id": 11, "amount": 1100.0, "category": "Electronics"},
    {"transaction_id": 54, "customer_id": 32, "amount": 440.0, "category": "Books"},
    {"transaction_id": 55, "customer_id": 92, "amount": 50.0, "category": "Groceries"},
    {"transaction_id": 56, "customer_id": 84, "amount": 4500.0, "category": "Electronics"},
    {"transaction_id": 57, "customer_id": 41, "amount": 500.0, "category": "Books"},
    {"transaction_id": 58, "customer_id": 32, "amount": 1100.0, "category": "Clothing"},
    {"transaction_id": 59, "customer_id": 84, "amount": 3000.0, "category": "Electronics"},
    {"transaction_id": 60, "customer_id": 15, "amount": 100.0, "category": "Groceries"},
    {"transaction_id": 57, "customer_id": 41, "amount": 240.0, "category": "Books"},
    {"transaction_id": 58, "customer_id": 32, "amount": 1200.0, "category": "Clothing"},
    {"transaction_id": 59, "customer_id": 84, "amount": 35000.0, "category": "Electronics"},
    {"transaction_id": 60, "customer_id": 15, "amount": 220.0, "category": "Groceries"},
]

is_equal(
    get_top_spenders(transactions, 6),
    [(15, 75319.0), (84, 42500.0), (32, 2740.0), (11, 1100.0), (41, 740.0), (21, 110.0)]
)
```

## Output 1

```
[(15, 75319.0), (84, 42500.0), (32, 2740.0), (11, 1100.0), (41, 740.0), (21, 110.0)]
```
