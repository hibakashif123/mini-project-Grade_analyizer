# Grade Analyzer

A Python program that analyzes student test scores and provides performance feedback.

## How to Use

1. Run the program
2. Enter test scores one at a time
3. When done entering scores, type "done"
4. See your statistics and performance analysis

## Example Output
Enter score: ('done'):85
Enter score: ('done'):90
Enter score: ('done'):78
Enter score: ('done'):88
Enter score: ('done'):92
Enter score: ('done'):done
average: 86.6
mode: 85
median: 88
Better! Need more work!
## What I Learned

- **Statistics Module**: Used `mean()`, `median()`, and `mode()` to analyze data
- **While Loops**: Used `while True` with `break` to ask for variable number of inputs
- **Input Validation**: Checked if user typed "done" before converting to integer
- **Conditionals**: Used `if/elif/else` to provide performance feedback
- **Lists**: Collected multiple scores and analyzed them
- **Type Conversion**: Converting strings to integers at the right time

## Code Breakdown

```python
# Import statistics functions
from statistics import mode, median, mean

scores = []

# Keep asking until user types "done"
while True:
    scores_input = input("Enter score (or 'done'): ")
    if scores_input == "done":
        break
    scores_input = int(scores_input)  # Convert AFTER checking
    scores.append(scores_input)

# Calculate statistics
average_value = mean(scores)
middle_value = mode(scores)
common_value = median(scores)

# Print results
print(f"average: {average_value}")
print(f"mode: {middle_value}")
print(f"median: {common_value}")

# Give feedback
if average_value > 85:
    print("Excellent!")
elif average_value >= 75:
    print("Good! Need more work!")
else:
    print("Needs improvement")
```

## Key Learning Points

- **Why separate input from int():** When you need to check for "done" before converting to a number
- **Why use while True with break:** To ask an unlimited number of times until user is done
- **Why append to list:** To collect all scores before calculating statistics
- **Why calculate AFTER loop:** Statistics functions need all data, not one at a time

## How to Run

```bash
python grade_analyzer.py
```

## Skills Practiced

- Using built-in modules (`statistics`)
- `while` loops with `break`
- Conditional logic (`if/elif/else`)
- Variable input with input validation
- Lists and `.append()`
- Type conversion (`int()`)
- F-string formatting
