# Clue 2: The Mismatched Fuel Cells

> [!INFO]
> You decoded the distress signal: *"Power failure. Backup fuel cells are the key."* Time to check the fuel cells!

## Challenge Details

| | |
| --- | --- |
| Name | `The Mismatched Fuel Cells` |
| Category | `dsa / hash maps` |
| Difficulty | `intermediate` |
| Flag format | `FLAG{some_words_here}` |

## Scenario

Iceberg-1's backup generator only starts when **exactly two fuel cells** are plugged in and their energy outputs add up to **4242 units**. Poco has scanned all 60 cells in storage:

```python
cells = [
    357, 2411, 344, 2635, 943, 2133, 2886, 2277, 1851, 1386,
    2007, 2498, 1956, 1581, 1327, 1117, 836, 2963, 1099, 435,
    2452, 1329, 2251, 2127, 1506, 1938, 1279, 2594, 399, 583,
    2196, 1812, 775, 1501, 722, 2102, 1827, 260, 2837, 417,
    2385, 2447, 1385, 1493, 2947, 1534, 2534, 2134, 2475, 1968,
    381, 483, 1205, 2041, 2955, 2820, 366, 348, 2973, 1368,
]
target = 4242
```

There is **exactly one** pair of cells that works. Find their **positions** (starting from 0) in the list, with the smaller position first.

Enter your answer as `i_j`. For example, if the cells were at positions 3 and 12, you would enter `3_12`. When you get it right, the page will reveal your flag!

## Getting Started

The simplest approach is to check every pair of cells with two loops. That works for 60 cells, but what if Poco had **a million**? A faster way is to use a **dictionary**: as you go through the list, remember each number you've seen and where, then ask "have I already seen the number I need?"

```python
seen = {}                      # number -> position
for position, value in enumerate(cells):
    needed = target - value
    # is "needed" already in seen? ...
    seen[value] = position
```

## Hints

<details>
<summary>Hint 1</summary>

For a cell worth `value`, its partner must be worth `target - value`.

</details>

<details>
<summary>Hint 2</summary>

Two nested `for` loops with `i` and `j > i` will work fine here. You can also try the dictionary approach.

</details>

<details>
<summary>Hint 3</summary>

`enumerate(cells)` gives you both the position and the value at the same time.

</details>

## TASK

**Question:** Which two positions? Enter them as `i_j` (smaller position first).

<div class="answer-box">
    <input class="answer-input" type="text" id="answer-1" placeholder="e.g. 3_12">
    <button class="answer-button" onclick="checkAnswer('answer-1', 'result-1', 'MTdfMjY=', 'RkxBR3tUdzBfU3VtX3QwX1RoM19NMDBufQ==')">Check Answer</button>
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

