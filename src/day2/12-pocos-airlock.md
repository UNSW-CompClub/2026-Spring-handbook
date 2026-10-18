# Poco's Airlock

## Challenge Details

| | |
| --- | --- |
| Name | `Poco's Airlock` |
| Category | `programming` |
| Difficulty | `medium` |
| Flag format | `FLAG{example_format}` |

## Scenario

You dock your shuttle against the Iceberg-I and step toward the airlock. The door doesn't open. Instead, a little screen blinks to life:

`== ICEBERG-I AIRLOCK ==`

It wants one number. No name, no password, just a number. Typical Poco.

Taped beside the screen is a sticky note: *"I got tired of pirates guessing my code, so I made the airlock listen to the ship's radio transmission instead. The passcode is the highest number of vowels you can find in any stretch of the message of a fixed length. - Poco"*

Poco left behind the raw transmission and a half-finished program. The transmission is long, so counting by hand isn't an option, and a slow solution will leave you standing at the door until the next orbit. Finish the program and recover the passcode.

Your flag will be of the format FLAG{[PEAK]}. For example, if the highest vowel count you find is 42, enter FLAG{42}.

## Files and Links

Starter code: 
```python
# Iceberg-I airlock -- starter code
# Fill in maxVowels, then run:  python3 starter.py
 
class Solution:
    def maxVowels(self, s: str, k: int) -> int:
        # TODO: return the maximum number of vowel letters
        # (a, e, i, o, u) in any substring of s with length k.
        pass
 
 
if __name__ == "__main__":
    sol = Solution()
 
    # LeetCode examples (Question 1)
    print("example 1:", sol.maxVowels("abciiidef", 3))   # expected 3
    print("example 2:", sol.maxVowels("aeiou", 2))       # expected 2
    print("example 3:", sol.maxVowels("leetcode", 3))    # expected 2
 
    # Real transmission (Question 2)
    with open("transmission.txt") as f:
        transmission = f.read().strip()
    print("transmission:", sol.maxVowels(transmission, 40000))
 
```

Download: 
<a href="airlock-docs/transmission.txt" download>transmission.txt</a>

Given a string `s` and an integer `k`, return the maximum number of vowel letters in any substring of `s` with length `k`.

Vowel letters in English are `'a'`, `'e'`, `'i'`, `'o'`, and `'u'`.

**Example 1:**

```
Input: s = "abciiidef", k = 3
Output: 3
Explanation: The substring "iii" contains 3 vowel letters.
```

**Example 2:**

```
Input: s = "aeiou", k = 2
Output: 2
Explanation: Any substring of length 2 contains 2 vowels.
```

**Example 3:**

```
Input: s = "leetcode", k = 3
Output: 2
Explanation: "lee", "eet" and "ode" contain 2 vowels.
```

**Constraints:**

- `1 <= s.length <= 10^5`
- `s` consists of lowercase English letters.
- `1 <= k <= s.length`

Complete the function in `starter.py`:

```python
class Solution:
    def maxVowels(self, s: str, k: int) -> int:
        
```

**Question:** What does `maxVowels("abciiidef", 3)` return? (Example 1, to check your function works.)

<div class="answer-box">
<input class="answer-input" type="text" id="answer" placeholder="Enter your answer">
<button class="answer-button" onclick="checkAnswer('answer', 'result', 'Mw==')">Check Answer</button>
</div>
<div id="result"></div>

**Question:** What does `maxVowels` return for the contents of `transmission.txt` with `k = 40000`?

<div class="answer-box">
<input class="answer-input" type="text" id="answer-2" placeholder="Enter your answer">
<button class="answer-button" onclick="checkAnswer('answer-2', 'result-2', 'Nzc1OQ==')">Check Answer</button>
</div>

<div id="result-2"></div>


> [!TIP]
> If you are not sure where to begin, check your function against the sample first. If that works but the real transmission takes forever, your approach is doing too much repeated work.

## Hints

<details>
<summary>Hint 1</summary>

Neighbouring substrings of the same length overlap almost completely.

</details>

<details>
<summary>Hint 2</summary>

Try to avoid recounting vowels you've already counted.

</details>


## Task

**Question:** What is the flag?

<div class="answer-box">
<input class="answer-input" type="text" id="answer-1" placeholder="Enter the flag">
<button class="answer-button" onclick="checkAnswer('answer-1', 'result-1', 'RkxBR3s3NzU5fQ==')">Check Answer</button>
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
