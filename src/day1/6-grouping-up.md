# Grouping up

## Challenge Details

| | |
| --- | --- |
| Category | `strings` |
| Difficulty | `hard` |
| Flag format | `FLAG{password}` |

## Scenario


A towel, [The Hitchhiker's Guide to the Galaxy] says, is about the most massively useful thing an interstellar hitchhiker can have. Partly it has great practical value. You can wrap it around you for warmth as you bound across the cold moons of Jaglan Beta; you can lie on it on the brilliant marble-sanded beaches of Santraginus V, inhaling the heady sea vapors; you can sleep under it beneath the stars which shine so redly on the desert world of Kakrafoon; use it to sail a miniraft down the slow heavy River Moth; wet it for use in hand-to-hand-combat; wrap it round your head to ward off noxious fumes or avoid the gaze of the Ravenous Bugblatter Beast of Traal (such a mind-boggingly stupid animal, it assumes that if you can't see it, it can't see you); you can wave your towel in emergencies as a distress signal, and of course dry yourself off with it if it still seems to be clean enough.

Heads up, Poco's successfully transmitted our next clue! However, the evil aliens have obscured the clue by inserting random letters in the mix. Your team has managed to narrow down the potential flags to the following:
- antragdlas
- illiadminourseems
- welhhikeassiveneatombatgin
- nciesasahandlieotheG
- dertbeneatroweimerenies 

Your task is to help them figure out which one is correct!

## Examples

How is the flag hidden? Well, we're told the flag is the only string which is NOT a **subsequence** of the original message. A **subsequence** is a new string generated from the original string with some characters (can be none) deleted. The **relative order of the remaining characters is left unchanged**. Here's a few simple examples to understand subsequences!

- ```ace``` is a subsequence of ```abcde```, since you can delete 'b' and 'd' from ```abcde``` to get ```ace```.
- ```a``` is a subsequence of ```abcde``` since you can delete 'bcde'.
- ```bb``` is NOT a subseuqnce of ```abcde```, since you cannot get ```bb``` by just deleting letters from ```abcde```.

> Ask a mentor if you're still in doubt!

## Your task
Now that you know exactly how the flag is hidden, here's your task:
- Write a program that determines whether a given string is a valid subsequence of the original message Poco transmitted.
- Test the options your team has narrowed down.

Your flag will be the only incorrect subsequence!

## Getting Started

Given that your program takes in a string ```word```, we want to know whether ```word``` is a valid subsequence of the `original_message` string stored in the function.

```python
def isSubsequence(word):
    original_message = '''A towel, [The Hitchhiker's Guide to the Galaxy] says, is about the most massively useful thing an interstellar hitchhiker can have. Partly it has great practical value. You can wrap it around you for warmth as you bound across the cold moons of Jaglan Beta; you can lie on it on the brilliant marble-sanded beaches of Santraginus V, inhaling the heady sea vapors; you can sleep under it beneath the stars which shine so redly on the desert world of Kakrafoon; use it to sail a miniraft down the slow heavy River Moth; wet it for use in hand-to-hand-combat; wrap it round your head to ward off noxious fumes or avoid the gaze of the Ravenous Bugblatter Beast of Traal (such a mind-boggingly stupid animal, it assumes that if you can't see it, it can't see you); you can wave your towel in emergencies as a distress signal, and of course dry yourself off with it if it still seems to be clean enough.'''
    
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
