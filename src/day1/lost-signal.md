# The Lost Signal

> [!INFO]
> Poco's space station, **Iceberg-1**, has gone dark. No one knows where it is, or how it disappeared. All we know is that Poco is missing...

## Challenge Details

| | |
| --- | --- |
| Name | `The Lost Signal` |
| Category | `misc / python basics` |
| Difficulty | `beginner` |
| Flag format | `FLAG{some_words_here}` |

## Scenario

Come tomorrow, Poco would've been missing for a whole month. It left to investigate some distress signals that were picked up by the agency, but the last message we received was "need more fish". Since then, no one's been able to find it. Not on it's flight path, nor around the source of the distress signals. Despite countless search parties, it seems that Poco has just vanished from the face of the universe. Just as you get up to call it a day, you see red flicker in the corner of your eye. It's a signal. You look closer, and see it's from the uncharted Sector 416B. You read the transmission, and begin to see characters. 

It's a message! Unfortunately, space radiation has scrambled it: between every real character, it looks like **two junk characters** have been sneaked in.

Here is the garbled transmission:

```text
F&qLw7Ab3Gpd{khPx40pyc8g0#p_anS0r3lynketi&_&2Sii0aaSnn}kk
```

Looks like you'll have to decode it!

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
