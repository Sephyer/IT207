# firstf.js

`firstf.js` is a custom command-line tool that combines the functionality of **Linux `grep` and `head`**. It searches for a specific pattern, but only within the first **N lines** of a file.

## Section 1 — Command Description

### What the Tool Does

The `firstf.js` program searches for a pattern within the first specified number of lines of a file.

Instead of searching the entire file like `grep`, `firstf.js` limits the search to the first **N lines**, similar to how the `head` command limits output to the beginning of a file.

For example, the following command searches for `cat` only within the first 10 lines of `test.txt`:

```bash
node firstf.js cat test.txt 10
```

The program prints the lines containing the pattern.

### How to Run It

The general command format is:

```bash
node firstf.js PATTERN FILENAME NUMBER_OF_LINES
```

Where:

* `PATTERN` — The word or text you want to search for.
* `FILENAME` — The file you want to search.
* `NUMBER_OF_LINES` — The number of lines from the beginning of the file that should be searched.

#### Example

```bash
node firstf.js computer test.txt 10
```

This searches for `computer` only in the first 10 lines of `test.txt`.

### Commands It Combines

`firstf.js` combines ideas from two Linux commands:

* **`grep`** — Searches text for a specified pattern.
* **`head`** — Limits the operation to the first N lines of a file.

The purpose of `firstf.js` is to combine these two behaviors into one JavaScript command.

Conceptually:

```text
head → select the first N lines
             ↓
grep → search those lines for a pattern
```

### Edge Cases

The program also considers situations such as:

* The specified file does not exist.
* The search pattern is empty.
* The requested number of lines is greater than the number of lines in the file.
* The pattern does not occur within the first N lines.
* An invalid value is provided for the number of lines.

For example:

```bash
node firstf.js elephant test.txt 10
```

If `elephant` does not appear in the first 10 lines, the program should indicate that no matching pattern was found.

---

## Section 2 — AI-Assisted Programming

### What I Asked AI

I asked AI to help me understand how to create and test a custom command that searches for a pattern within the first N lines of a file.

I specifically asked AI for:

* An explanation of how `firstf.js` should work.
* Test cases for the command.
* Edge cases that could cause problems.
* Examples of input and expected output.
* Help explaining the JavaScript code.

### Where AI Helped

AI helped identify several test scenarios and edge cases that I could use to evaluate my program.

For example, AI suggested testing:

1. A pattern that appears multiple times.
2. A pattern that does not appear.
3. A pattern that appears after the first N lines.
4. A file that does not exist.
5. A number of lines that is larger than the file.

### Where I Had to Think Independently

I had to determine how the suggested tests applied to my specific implementation and verify the results by actually running the commands.

I also had to decide how the program should behave when the pattern is not found and when the requested number of lines is greater than the number of lines in the file.

After testing the program, I compared the actual output with the expected output and made changes to the implementation where necessary.

### What AI Got Wrong or Missed

AI did not always account for the exact implementation of my code. For example, one issue was that the code attempted to use `lines.length` before the `lines` variable had been created.

