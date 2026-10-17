# Clue 8: Poco's Toys

> [!INFO]
> We need to find Poco's toys in order to figure out a secret code hidden inside a toy!

## Challenge Details

| | |
| --- | --- |
| Name | `Save Poco's toys!` |
| Category | `crypto` |
| Difficulty | `intermediate` |
| Flag format | `FLAG{example_format}` |

## Scenario

Poco's toys have been lost to space! Thankfully, we have received strings of 7 characters that tell us where they are in space.

- ["tuvwxyz", "igkmoqs", "olpqrst", "axczevt", "rospqrr", "spqtuvv", "wxyzaaa", "omqsuwy", "gijklll", "wxyzaaa", "tuvwxyz", "jlnprtv", "spqtuvv", "axczevt", "ywaxcze", "czetwux", "axczevt", "ywaxcze", "wxyzaaa", "wxyzaaa", "spqtuvv", "czetwux", "axczevt", "axczevt", "rospqrr"]

Poco has a bunch of boomerangs that can get his toys back, and we know that a given toy is on the same line as another toy if you can take its string and shift every single letter forward or backward by the same number of spots in the alphabet (where 'z' wraps right back around to 'a').

For example, if Toy A is "abcde" and Toy B is "bcdef" -> Shifting "tuvwxyz" forward by 1 letter gives "bcdef" which matches perfectly! They are on the same line, so 1 boomerang can grab both.

Please find the smallest amount of boomerangs poco needs to get all his toys.

## Hints

<details>
<summary>Hint 1</summary>

Maybe this problem would be easier if you found a way to see how different each word is?

</details>

<details>
<summary>Hint 2</summary>

With the following code:
```python
        def standardize(word):
            outputList = [0]

            for i in range(1, len(word)):
                outputList.append((ord(word[i]) - ord(word[0])) % 26)

            return tuple(outputList)
```

"abc" and "bcd" both make (0,1,2)...

</details>

<details>
<summary>Hint 3</summary>

If you stored how many unique tuples the list makes, maybe you'll get your answer?

</details>

## Task

**Question:** What is the flag?

<div class="answer-box">
    <input class="answer-input" type="text" id="answer-1" placeholder="Enter the flag">
    <button class="answer-button" onclick="checkAnswer('answer-1', 'result-1', 'RkxBR3sxMX0=')">Check Answer</button>
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
