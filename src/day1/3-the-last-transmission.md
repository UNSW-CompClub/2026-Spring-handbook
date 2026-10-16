# Clue 3: The Last Transmission

> [!INFO]
> The airlock is sealed and Iceberg-1 is warming up again. Poco sends one last message home, but something about it looks a little odd...

## Challenge Details

|             |                         |
| ----------- | ----------------------- |
| Name        | `The Last Transmission` |
| Category    | `misc / python basics`  |
| Difficulty  | `beginner`              |
| Flag format | `FLAG{some_words_here}` |

## Scenario

Mission control receives Poco's final report. It looks normal at first, but a few letters are in **capitals** where they shouldn't be. Poco has hidden a secret word in them!

```text
Power is back On and the pipes are fixed. the Crew is cOsy and the heater is hummIng again. the airlock is Sealed tight and every System on the stAtion looks normal For now. sEe you soon, mission control.
```

Read the capital letters from left to right to find the secret word.

Enter your answer as the secret word. For example, if the capitals spelled `HELLO`, you would enter `HELLO`. When you get it right, the page will reveal your flag!

## Getting Started

You could pick out the capitals by eye, but it's easy to miss one. Instead, go through the message one character at a time and only keep the capital letters. Python has a handy check for that: `.isupper()` is `True` for capital letters and `False` for everything else.

```python
secret = ""
for letter in message:
    # is this letter a capital?
print(secret)
```

## Hints

<details>
<summary>Hint 1</summary>

`'P'.isupper()` gives `True`, and `'p'.isupper()` gives `False`.

</details>

<details>
<summary>Hint 2</summary>

You can add a letter onto the end of a string with `secret = secret + letter`.

</details>

<details>
<summary>Hint 3</summary>

Spaces, full stops and commas aren't capitals, so `.isupper()` skips them for you.

</details>

## TASK

**Question:** What is the secret word?

<div class="answer-box">
    <input class="answer-input" type="text" id="answer-1" placeholder="e.g. HELLO">
    <button class="answer-button" onclick="checkAnswer('answer-1', 'result-1', 'UE9DT0lTU0FGRQ==', 'RkxBR3tQMGMwXzFzX1M0ZjN9')">Check Answer</button>
</div>

<div id="result-1"></div>

<script>
function checkAnswer(inputId, resultId, enAnswer, enFlag) {
const input = document.getElementById(inputId);
const result = document.getElementById(resultId);
let correctAnswer, flag;

try {
            correctAnswer = atob(enAnswer);
            flag = enFlag ? atob(enFlag) : '';
        } catch (e) {
            result.className = 'error';
            result.textContent = 'Error decoding the answer. Please contact support.';
            result.style.display = 'block';
return;
        }

if (input.value.trim().toLowerCase() === correctAnswer.toLowerCase()) {
            result.className = 'correct';
            result.textContent = 'Correct! Your flag is: ' + flag;
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
