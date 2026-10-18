# Poco's Airlock

## Challenge Details

| | |
| --- | --- |
| Name | `Poco's Airlock` |
| Category | `reverse engineering` |
| Difficulty | `beginner` |
| Flag format | `FLAG{example_format}` |

## Scenario

You dock your shuttle against the Iceberg-I and step toward the airlock. The door doesn't open. Instead, a little screen blinks to life:

`== ICEBERG-I AIRLOCK ==`

It wants two numbers. No name, no password, just numbers. Typical Poco.

Taped beside the screen is another sticky note: *"I got tired of pirates guessing my code, so I made the airlock listen to the ship's radio transmission instead. It scans a short window of the message and counts the vowels. The busiest window wins. - Poco"*

Thankfully, Poco left the airlock program running on a nearby terminal, and you can read its source code. Figure out how big the scanning window is and what the highest vowel count in any window of that size turns out to be.

Your flag will be of the format FLAG{[WINDOW]_[PEAK]}. For example, if you think the window size is 12 and the peak vowel count is 7, enter FLAG{12_7}.

## Files and Links

Starter code:
```python
class Solution:
    def maxVowels(self, s: str, k: int) -> int:
        
```

Transmission file: 
<a href="airlock-docs/transmission.txt" download>transmission.txt</a>

**Question:** What is the window size the airlock uses?

<div class="answer-box">
<input class="answer-input" type="text" id="answer" placeholder="Enter your answer">
<button class="answer-button" onclick="checkAnswer('answer', 'result', 'NQ==')">Check Answer</button>
</div>
<div id="result"></div>

**Question:** What is the peak (maximum) number of vowels in any window of that size in Poco's transmission?

<div class="answer-box">
<input class="answer-input" type="text" id="answer-2" placeholder="Enter your answer">
<button class="answer-button" onclick="checkAnswer('answer-2', 'result-2', 'NA==')">Check Answer</button>
</div>

<div id="result-2"></div>


> [!TIP]
> If you are not sure where to begin, run the program and try a couple of random numbers. Then open the source and see what it compares your guesses against.

## Hints

<details>
<summary>Hint 1</summary>

The window size isn't written as a plain number. Python can evaluate the expression for you. Try pasting it into a Python prompt.

</details>

<details>
<summary>Hint 2</summary>

Vowels here are only `a`, `e`, `i`, `o`, `u`. Spaces and consonants don't count. You can slide a window across the transmission by hand, or write a few lines of code to do it.

</details>


## Task

**Question:** What is the flag?

<div class="answer-box">
<input class="answer-input" type="text" id="answer-1" placeholder="Enter the flag">
<button class="answer-button" onclick="checkAnswer('answer-1', 'result-1', 'RkxBR3s1XzR9')">Check Answer</button>
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
