# Poco's Birthday

## Challenge Details

| | |
| --- | --- |
| Name | `Poco's Birthday?` |
| Category | `reverse engineering` |
| Difficulty | `beginner` |
| Flag format | `FLAG{example_format}` |

## Scenario

And with that, you head to the edge of Sector 416B. Once you get there in your shuttle, you see the Iceberg-I! It seems to be orbiting a ringed gas-giant. Looks like Poco found a new exoplanet. Perhaps Poco's exploring the moons? Who knows. 

You get to the Iceberg-I, but are stopped from boarding. Looks like you need a passcode.

You wonder what it could be. Poco's favourite song, favourite movie, favourite toy. You look to the left of the keyboard and see a sticky note with a hint! Looks like we need to figure out Poco's age and it's favourite colour to move on!

Thankfully, Poco wrote a program a few months ago that tells us how old it is and its favorite color. Help us recover this info about our penguin pal!

Your flag will be of the format FLAG{[AGE][COLOR]}. For example, if you think Poco is 97 and its favourite color is orange, enter FLAG{97orange}.

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


> [!TIP]
> If you are not sure where to begin, try putting in a random number\color and see what happens!

## Hints

<details>
<summary>Hint 1</summary>

Poco graduated high school recently so it shouldn't be that old...

</details>

<details>
<summary>Hint 2</summary>

We're pretty sure Poco's favourite color appears on a rainbow...

</details>


## Task

**Question:** What is the flag?

<div class="answer-box">
    <input class="answer-input" type="text" id="answer-1" placeholder="Enter the flag">
    <button class="answer-button" onclick="checkAnswer('answer-1', 'result-1', 'RkxBR3sxOHJlZH0=')">Check Answer</button>
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
            result.textContent = '✓ Correct Answer!';
        } else {
            result.className = 'incorrect';
            result.textContent = '✗ Incorrect. Try again!';
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
