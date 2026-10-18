# Clue 10: Sealing the Airlock

> [!INFO]
> You try and start the generator. _"Frozen pipes burst."_ The burst pipes cracked an airlock seal. Time to fix it!

## Challenge Details

|             |                         |
| ----------- | ----------------------- |
| Name        | `Sealing the Airlock`   |
| Category    | `dsa / stacks`          |
| Difficulty  | `intermediate`          |
| Flag format | `FLAG{some_words_here}` |

## Scenario

Iceberg-1's airlock is held shut by clamps. There are three kinds: `( )`, `[ ]` and `{ }`. A seal pattern only works if every clamp is closed by the **same kind** it was opened with, and the **last clamp opened is always the first one closed**. So `([]{})` works, but `([)]` and `(()` don't.

Poco found five seal patterns in the airlock manual:

```text
1: ((][)){}{{{([{(())}]){}[{[]{}{}}{(({}))}]}}}
2: [[]{}(({{}})){}(([{()}{{}}[]]()({({})})))](
3: {}{}()({})()(({{}})([])())[({}({[{}[]]}))]
4: ]{[{{}}{}[]]}{{}}{}([]){{}{([])}}[({})][
5: [())[](]((){}{(()(()))[]{{[]}{((){}())}}})
```

There is **exactly one** pattern that works. Find its number.

Enter your answer as a single number.

## Getting Started

Counting the clamps won't work, because `([)]` has one of each and still fails. Instead, use a **stack**: a list where you only add to and take from the end. Every time a clamp opens, put it on the stack. Every time a clamp closes, take the top one off and check that it matches.

```python
# closing clamp -> opening clamp
pairs = {')': '(', ']': '[', '}': '{'}
stack = []
for clamp in pattern:
    if clamp in '([{':
        stack.append(clamp)
    # otherwise, does it match what's on top of the stack?
```

## Hints

<details>
<summary>Hint 1</summary>

`stack.append(x)` puts `x` on top of the stack, and `stack.pop()` takes the top item off and gives it back to you.

</details>

<details>
<summary>Hint 2</summary>

If a closing clamp shows up while the stack is empty, there is nothing for it to close, so the pattern fails.

</details>

<details>
<summary>Hint 3</summary>

When the loop finishes, the stack should be empty. Anything left over was opened but never closed.

</details>

## TASK

**Question:** Which pattern works? Enter its number.

For this challenge, submit:

1. The flag.
2. The main thing that helped you solve it.
3. A short explanation of how the challenge works.
