# CTF Challenge Template

This page can be used for a CTF challenge, puzzle, exploit, or investigation task.

> [!INFO]
> Replace the example details, files, and hints before using this page for a real challenge.

## Challenge Details

| | |
| --- | --- |
| Name | `How old is Poco?` |
| Category | `reverse engineering` |
| Difficulty | `beginner` |
| Time | `10 minutes` |
| Flag format | `FLAG{example_format}` |

## Scenario

Poco's birthday is coming up, but we forgot how old he is!

Thankfully, Poco wrote a program a few months ago that tells us how old he is and his favorite color. Help us recover this info about our penguin pal!

Your flag will be of the format FLAG{[AGE][COLOR]}. For example, if you think Poco is 97 and his favourite color is orange, enter FLAG{97orange}.

## Files and Links

**Question:** How old is Poco?

<div class="answer-box">
    <input class="answer-input" type="text" id="answer" placeholder="Enter your answer">
    <button class="answer-button" onclick="checkAnswer('answer', 'result', 'MTg=')">Check Answer</button>
</div>
<div id="result"></div>

**Question:** Whats Poco's favourite color? Enter your answer in all lowercase

<div class="answer-box">
    <input class="answer-input" type="text" id="answer-2" placeholder="Enter your answer">
    <button class="answer-button" onclick="checkAnswer('answer-2', 'result-2', 'cmVk')">Check Answer</button>
</div>

<div id="result-2"></div>

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
            result.textContent = '✓ Correct Answer!';
        } else {
            result.className = 'incorrect';
            result.textContent = '✗ Incorrect. Try again!';
        }

        result.style.display = 'block';
    }
</script>

> [!TIP]
> If you are not sure where to begin, try putting in a random number\color and see what happens!

## Hints

<details>
<summary>Hint 1</summary>

Poco graduated high school recently so he shouldn't be that old...

</details>

<details>
<summary>Hint 2</summary>

We're pretty sure Poco's favourite color appears on a rainbow...

</details>


## Task

> [!SUCCESS] Capture the flag
> Find the flag and explain how you found it.

For this challenge, submit:

1. The flag.
2. The main thing that helped you solve it.
3. A short explanation of how the challenge works.
