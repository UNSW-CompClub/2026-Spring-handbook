# Clue 2: Hexidecimal Hodgepodge

> [!INFO]
> You got Poco’s SOS! Now the station computer is trying to talk, but it’s running on emergency power and can only send raw hex.

## Challenge Details

|             |                           |
| ----------- | ------------------------- |
| Name        | `Hexadecimal  Hodgepodge` |
| Category    | `crypto`                  |
| Difficulty  | `beginner`                |
| Flag format | `FLAG{example_format}`    |

## Scenario

We have received the following message that we can't quite understand. Help us decode it, and you might just get your flag!

- 46 4c 41 47 7b 49 53 75 72 65 48 6f 70 65 54 68 69 73 4d 65 73 73 61 67 65 44 6f 65 73 6e 74 47 65 74 48 65 78 43 6f 64 65 64 7d

## Useful Commands

It looks like you can convert a hexadecimal number to a readable character in python like this:

```python

hexadecimal_character = '46'
translated_character = chr(int(i, 16)) # <- This becomes 'F', which is correct!

```

## Hints

<details>
<summary>Hint 1</summary>

It looks like we can split the string into a list of characters....

</details>

<details>
<summary>Hint 2</summary>

And once we have our list, maybe we can do the translation **for** every character in a sort of **loop**?

</details>

## Task

**Question:** What is the flag?
> Find the flag and explain how you found it.

For this challenge, submit:

1. The flag.
2. The main thing that helped you solve it.
3. A short explanation of how the challenge works.
