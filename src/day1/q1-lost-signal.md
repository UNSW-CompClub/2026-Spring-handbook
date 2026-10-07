# Clue 1: The Lost Signal

> [!INFO]
> Poco's space station, **Iceberg-1**, has gone dark and nobody knows why. Solve three clues to find out what happened!

## Challenge Details

| | |
| --- | --- |
| Name | `The Lost Signal` |
| Category | `misc / python basics` |
| Difficulty | `beginner` |
| Flag format | `FLAG{some_words_here}` |

## Scenario

Poco is floating aboard Iceberg-1 when mission control sends a distress message. Unfortunately, space radiation has scrambled it: between every real character, **two junk characters** have been sneaked in.

Here is the garbled transmission:

```text
F&qLw7Ab3Gpd{khPx40pyc8g0#p_anS0r3lynketi&_&2Sii0aaSnn}kk
```

Help Poco recover the real message. The flag is the clean message.

## Useful Commands

Python lets you grab characters from a string at regular steps using **slicing**:

```python
word = "abcdefgh"

print(word[0])     # 'a'  (the first character)
print(word[2:5])   # 'cde' (characters 2, 3 and 4)
print(word[::2])   # 'aceg' (every 2nd character)
```

## Hints

<details>
<summary>Hint 1</summary>

Look at the start of the message: `F`, then two junk letters, then `L`... how often do the real characters show up?

</details>

<details>
<summary>Hint 2</summary>

The real characters appear at positions 0, 3, 6, 9, ... Try `message[::3]`.

</details>

## TASK

**Question:** What is the flag?

<div class="answer-box">
    <input class="answer-input" type="text" id="answer-1" placeholder="Enter the flag">
    <button class="answer-button" onclick="checkAnswer('answer-1', 'result-1', 'RkxBR3tQMGMwX1MzbnRfUzBTfQ==')">Check Answer</button>
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

        if (input.value.trim().toLowerCase() === correctAnswer.toLowerCase()) {
            result.className = 'correct';
            result.textContent = 'Correct Answer!';
        } else {
            result.className = 'incorrect';
            result.textContent = 'Incorrect. Try again!';
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
