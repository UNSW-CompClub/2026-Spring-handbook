# Reversing the A-Game

## Challenge Details

| | |
| --- | --- |
| Category | `reversing` |
| Difficulty | `intermediate` |
| Flag format | `FLAG{password}` |

## Scenario

Great news: we've been transmitted a password to unlock where Poco's trapped! Here it is:
*The exceptionally ostentatious bioengineer continuously maneuvered through the subterranean laboratory, meticulously evaluating a series of queueing, highly ambiguous, and deeply unidentifiable archaeological anomalies.*

Bad news: Poco's attept to transmit the password got a bit lost in translation, and all the vowels got reversed.

We need to figure out a way to **reverse all the vowels** (and only the vowels!) in order to get the original password back.

> 'Vowels' refers to the standard vowels in English: 'a', 'e', 'i', 'o', and 'u'

Your flag will be every second word of the resulting sentence, for example:
1. Original password: Hello how are you?
2. (after running it through your function) new password = Hullo hew aro yoe? (vowels are reversed)
3. Your flag: `Hullo_aro` (first word, then every alternating word)

## Examples

What does 'reversing the vowels' mean? Here's a few examples to help make it clear what Poco wants!
<details>
<summary>Input: "IceCreAm"</summary>

Expected output: "AceCreIm"

Why? We reverse the vowels I, e, e, A to form the expected output!

</details>

<details>
<summary>Input: "Save Poco :("</summary>

Expected output: "Sovo Peca :("

Why? We reverse the vowels a, e, o, o to form the expected output!
> What happens to any character that's not a letter?

</details>

## Getting Started

Given that program takes in a string ```original_password```, consider what you need to add to your function to reverse the vowels in ```original_password``` and return ```correct_password```:

```python
def reverseVowels(original_password):
    # your logic goes here!
    return correct_password
```

## Hints
<details>
<summary>Hint 1</summary>
How would you isolate just the vowels from the original string? Do you need to store them somewhere?

</details>

<details>
<summary>Hint 2</summary>

How would you access the vowels in reverse-order?
</details>


## Task
> Find the flag and explain how you found it!

For this challenge, submit:

1. The flag.
2. The main thing that helped you solve it.
3. A short explanation of how the challenge works.
