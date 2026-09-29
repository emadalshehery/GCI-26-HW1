# Homework 1: Efficient Data Manipulation Using NumPy

**Deadline:** Thu, Oct 8, 2026 (11:00 UTC)
**Notebook:** `HW1_for_Session2.ipynb`
**Submission:** Omnicampus → *Python code submission*

## Task

Implement `homework(a)`, which takes a 1D NumPy array of integers and returns a new array containing only the elements that are **multiples of 5 and odd**.

```python
homework(a: np.ndarray) -> np.ndarray
```

| Argument | Type         | Description                 |
|----------|--------------|-----------------------------|
| `a`      | `np.ndarray` | 1D NumPy array of integers  |

**Returns:** `np.ndarray` of elements that are both multiples of 5 and odd.

## Example

```python
a = np.array([1, 5, 10, 3, 4, 25, 30])
print(homework(a))   # [ 5 25]
```

## Solution

```python
def homework(a):
    return a[(a % 5 == 0) & (a % 2 == 1)]
```

A boolean mask selects the elements in one vectorized step, with no loops. NumPy's `%` follows Python semantics, so negative odd multiples (e.g. `-5`) are handled correctly.

## Test Cases

| # | Input                              | Expected output |
|---|------------------------------------|-----------------|
| 1 | `[1, 5, 10, 3, 4, 25, 30]`         | `[ 5 25]`       |
| 2 | `[11, 15, 20, 21, 35, 40, 45]`     | `[15 35 45]`    |
| 3 | `[2, 4, 6, 8]`                     | `[]`            |

The grader also uses hidden cases (e.g. negative values, no matches).

## Running

```bash
pip install numpy jupyter
jupyter notebook HW1_for_Session2.ipynb
```

Run the cells top to bottom. Re-run the `homework()` cell after every edit.

## Submission Rules

- Submit only the complete `homework()` function (from `def` to `return`).
- No `import` statements, downloads, or data loading inside the function.
- Remove the `# Write your answer here` comment.
- Keep everything in a single function that returns a numeric array.

## Grading Notes

- Your **latest** submission is your final grade, not the highest.
- Late submissions earn at most **2.0** points (instead of 3.0).
- If your latest submission already shows `3.0`, don't resubmit during the late window.
- You may submit as many times as needed.
