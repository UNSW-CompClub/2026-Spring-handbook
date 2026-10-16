# Clue 6: Grouping up

> [!INFO]
> The storage bay door slides open and Poco floats out, safe at last! There's just one problem: the escape shuttle is locked. Poco has the launch code, but the signal seems to be scrambled. Fix it and bring Poco home!

## Challenge Details

|             |                  |
| ----------- | ---------------- |
| Category    | `strings`        |
| Difficulty  | `hard`           |
| Flag format | `FLAG{password}` |

## Scenario

Heads up, Poco's successfully transmitted our next clue! However, the evil aliens have obscured the clue by inserting random letters in the mix. Your team has managed to narrow down the potential flags to the following:

- option1
- option2
- option3
- option4
- option5

Your task is to help them figure out which one is correct!

## Examples

How is the flag hidden? Well, we're told it must be a **subsequence** of the original message, ie it's a new string generated from the original string with some characters (can be none) deleted. The **relative order of the remaining characters is left unchanged**. Here's a few simple examples to understand subsequences!

- `ace` is a subsequence of `abcde`, since you can delete 'b' and 'd' from `abcde` to get `ace`.
- `a` is a subsequence of `abcde` since you can delete 'bcde'.
- `bb` is NOT a subseuqnce of `abcde`, since you cannot get `bb` by just deleting letters from `abcde`.

> Ask a mentor if you're still in doubt!

## Your task

Now that you know exactly how the flag is hidden, here's your task:

- Write a program that determines whether a given string is a valid subsequence of the original message Poco transmitted.
- Test the options your team has narrowed down.

Your flag will be the correct subsequence!

## Getting Started

Given that your program takes in a string `original_password`, and a string `word`, we want to know whether `word` is a valid subsequence of `original_password`.

```python
def isSubsequence(original_password, word):
    # your logic goes here!
    return true
```

> What does it mean if our function returns true? What if it returns false?

## Hints

<details>
<summary>Hint 1</summary>
If you wanted to do this by hand, how would you track your letters in the word and original_password? 
In other words, We want to track two positions at the same time.

With your knowledge of arrays and keeping track of positions in arrays, can you think of how to do this?

</details>

<details>
<summary>Hint 2</summary>
If we had one pointer for the word and one for the original_password, when do you increment each one?
You want to loop until you haven't run out of letters in the original_password!
</details>

<details>
<summary>Hint 3</summary>
When do you know you have a match? Can we compare the word pointer with the expected length of the word?

</details>

## Task

> Find the flag and explain how you found it!

For this challenge, submit:

1. The flag.
2. The main thing that helped you solve it.
3. A short explanation of how the challenge works.
