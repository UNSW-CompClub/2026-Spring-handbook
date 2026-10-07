# Clue 3: The Escape Route

> [!INFO]
> With the generator running, Iceberg-1's lights flicker back on. Then the alarms start. Someone has sealed the corridors, and Poco needs to get to the escape pod!

## Challenge Details

| | |
| --- | --- |
| Name | `The Escape Route` |
| Category | `dsa / graphs` |
| Difficulty | `advanced` |
| Flag format | `FLAG{some_words_here}` |

## Scenario

Here is a map of Iceberg-1:

```text
.#......###...#.
.S..#...........
........#.......
..#.#..#....##..
##......#.......
#......#..#.....
..##.#....##.#.#
##.......#.##.E#
.........#..#...
```

- `S` is where Poco is standing.
- `E` is the escape pod.
- `.` is an open floor tile.
- `#` is a sealed wall that Poco can't walk through.

Poco can move **up, down, left or right** by one tile at a time (no diagonals).

Your answer has two numbers, entered as `N_M`:

1. **N**, the steps: the fewest moves Poco needs to get from `S` to `E`.
2. **M**, the tiles: how many tiles Poco can reach in total from `S`, counting `S` and `E` themselves.

For example, `20_150` means a shortest path of 20 moves and 150 reachable tiles. When you get it right, the page will reveal your flag!

## Getting Started

You *could* trace the path by eye, but counting every reachable tile by hand is slow and easy to get wrong. Let's get Python to explore the map for us!

A **BFS (breadth-first search)** explores outwards from `S` in rings: first every tile 1 move away, then every tile 2 moves away, and so on. The first time it reaches `E`, that is guaranteed to be the shortest path.

Think of it like a queue at a canteen: whoever joins first gets served first. Here is most of the code. Fill in the `???` parts:

```python
from collections import deque

grid = [
    ".#......###...#.",
    ".S..#...........",
    "........#.......",
    "..#.#..#....##..",
    "##......#.......",
    "#......#..#.....",
    "..##.#....##.#.#",
    "##.......#.##.E#",
    ".........#..#...",
]

rows = len(grid)
cols = len(grid[0])

# Poco starts at row 1, column 1
queue = deque([(1, 1, 0)])   # (row, col, steps so far)
visited = {(1, 1)}           # tiles we've already seen

while queue:
    row, col, steps = queue.popleft()

    if grid[row][col] == "E":
        print("Steps to the pod:", ???)

    # look at the 4 neighbouring tiles
    for dr, dc in [(1, 0), (-1, 0), (0, 1), (0, -1)]:
        new_row = row + dr
        new_col = col + dc

        # stay on the map
        if 0 <= new_row < rows and 0 <= new_col < cols:
            # skip walls and tiles we've already seen
            if grid[new_row][new_col] != "#" and (new_row, new_col) not in visited:
                visited.add((new_row, new_col))
                queue.append((???, ???, ???))

print("Reachable tiles:", ???)
```

> [!TIP]
> Not sure how BFS works? Try it on paper first. Put `S` in the queue, then write down its neighbours, then *their* neighbours. You'll see the rings grow outwards.

## Hints

<details>
<summary>Hint 1</summary>

`popleft()` takes the oldest tile out of the queue. `append()` adds a new tile to the back.

</details>

<details>
<summary>Hint 2</summary>

Each neighbour is one move further than the tile we came from, so its step count is `steps + 1`.

</details>

<details>
<summary>Hint 3</summary>

The first `???` is the number of steps stored with `E`. The last `???` is how many tiles are in `visited` (try `len(visited)`).

</details>

<details>
<summary>Hint 4</summary>

The `queue.append` line needs three values: the new row, the new column, and the new step count.

</details>

## TASK

**Question:** What are the steps and the reachable tiles? Enter them as `N_M`.

<div class="answer-box">
    <input class="answer-input" type="text" id="answer-1" placeholder="e.g. 20_150">
    <button class="answer-button" onclick="checkAnswer('answer-1', 'result-1', 'MjFfMTA4', 'RkxBR3tCRlNfZzB0X1BvYzBfSDBtZX0=')">Check Answer</button>
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
