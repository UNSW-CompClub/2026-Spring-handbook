# Hexadeimcal Hodgepodge

## Challenge Details

| | |
| --- | --- |
| Name | `Hexadecimal  Hodgepodge` |
| Category | `crypto` |
| Difficulty | `beginner` |
| Flag format | `FLAG{example_format}` |

## Scenario

You board Poco's ship and look around. You check the fuel cells, the map room, the cafeteria. Clues everywhere, but nothing that says Poco is still on board. You make your way to the bridge and see a flashing red dot next to the comms. It's another signal!

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

<div class="answer-box">
    <input class="answer-input" type="text" id="answer-1" placeholder="Enter the flag">
    <button class="answer-button" onclick="checkAnswer('answer-1', 'result-1', 'RkxBR3tJU3VyZUhvcGVUaGlzTWVzc2FnZURvZXNudEdldEhleENvZGVkfQ==')">Check Answer</button>
</div>

<div id="result-1"></div>

<script>
    function checkAnswer(inputId, resultId, enAnswer) {
        const input = document.getElementById(inputId);
        const result = document.getElementById(resultId);
        let correctAnswer;

        try {
            correctAnswer = atob(enAnswer);
        } catch (e) {
            result.className = 'error';
            result.textContent = 'Error decoding the answer. Please contact support.';
            result.style.display = 'block';
            return;
        }

        if (input.value.trim() == correctAnswer) {
            result.className = 'correct';
            result.textContent = 'Correct Answer!';
        } else {
            result.className = 'incorrect';
            result.textContent = 'Incorrec. Try again!';
        }

        result.style.display = 'block';
    }
</script>

> [!SUCCESS] Capture the flag
> Find the flag and explain how you found it.

For this challenge, submit:

1. The flag.
2. The main thing that helped you solve it.
3. A short explanation of how the challenge works.
