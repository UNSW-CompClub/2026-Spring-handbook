# Unique key

## Challenge Details

| | |
| --- | --- |
| Category | `cyptography` |
| Difficulty | `medium` |
| Flag format | `FLAG{number}` |

## Scenario

A rogue alien server is blasting a massive list of integers across Poco's transmission line!
Your team has figured out that every token on the network has a twin that effectively cancels it out. However, the aliens left behind exactly **one unique integer token**. 

This unique integer is the key to powering our rocket to find Poco. Find it, and you find the flag!

## Examples

- If you have the numbers [1, 5, 42, 5, 1], your unique key is 42!
- If you have the numbers [1, 3, 3, 1, 2], your unique key is 2!


## Getting Started
- Download the input.txt provided.
- Complete the function below to find the unique key

Your team has taken care of the file-handling aspect of the function, all you have to do is complete the function and find the key!

```python
def find_flag(filename="input.txt"):
    result = 0 # track the key we've found
    
    # this opens the file safely and loops through it line by line
    with open(filename, "r") as f:
        for line in f:
            # strip() removes invisible newline characters (\n)
            # int() converts the text string into a usable integer
            number = int(line.strip())
            
            # your logic goes here!
           
            pass # remove this line once you've added your code

    # print the final answer inside the flag format: flag{NUMBER}
```


## Hints
<details>
<summary>Hint 1: brute force</summary>
What's the simplest solution you can think of? What if you count the occurrence of each number provided?

</details>

<details>
<summary>Hint 2: XOR</summary>
A more efficient way to solve this problem would be to compare every number one by one. If we encounter the same number, we want to cancel them out. Otherwise, we want to keep the new number.

Fortunately, we have the perfect operator for this: The bitwise operator **XOR** (which stands for exclusive OR, and is represented by `^`)!
This operator has two very useful properties:
- Any number XOR'd with itself becomes 0: `X ^ X = 0` (ie they cancel out!)
- Any number XOR'd with 0 stays the same: `X ^ 0 = X` (ie we get the unique number)

The order in which you perform XOR operations does not matter (think 1 + 2 = 2 + 1). This means you can think of all duplicates pairing up, XOR-ing to 0, and cancelling out! What does that leave you with?

Here's an example:
Imagine our file has the numbers: 1, 5, 42, 5, 1. Our unique key in this case would be 42.
If you start with 0, and XOR every number into it, we have something like the following:
```
result = 0 ^ 1 ^ 5 ^ 42 ^ 5 ^ 1
```

Since order doesn't matter, we can think of this as
```
result = 0 ^ (1 ^ 1) ^ (5 ^ 5) ^ 42
```

Now, what happens if we consider our first XOR property? Can you reason out why the pairs become 0?
```
result = 0 ^ 0 ^ 0 ^ 42
```
Now, considering our second XOR property:
```
result = 42
```

The duplicates have vanished, leaving us with our unique key!
</details>

## Task
> Find the flag and explain how you found it!

For this challenge, submit:

1. The flag.
2. The main thing that helped you solve it.
3. A short explanation of how the challenge works.
