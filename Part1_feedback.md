# ASSESSMENT FEEDBACK --- PART 1 (REFORMATTED)

====================================================== \## PROBLEM 1 ---
LIBRARY BOOK TRACKER
======================================================

### 1. CODE QUALITY & CORRECTNESS

✓ All required functionality implemented: adding books/customers,
checking out, returning, displaying the catalogue, and viewing a
customer's borrowed books.\
✓ Strong validation for duplicates, casing, and missing records.\
✓ Demonstration clearly shows intended behaviour and error handling.

**Improvements:**\
- Books identified *only by title*, not by a unique ID → fragile when
two books share a title.\
- `borrowing_book()` has an incorrectly indented error message,
preventing it from firing reliably.\
- Customers store *only the title* when borrowing, rather than a unique
ID or object → removal relies on exact title matching.\
- `return_book` trusts borrower_id consistency; mismatches are not
validated.

### 2. DEMONSTRATION & ROBUSTNESS

✓ Includes good demonstrations of duplicates, missing books, invalid
customer IDs, and case-insensitive lookup.

**Missing robustness tests:**\
- Returning a book borrowed by a *different* customer.\
- Customer name casing mismatch ("tOm Smith").\
- Corrupted catalogue/customer state.

**Example failure:**\
Appending `None` to a customer's borrowed list → printed output includes
`None` without any error or validation.

------------------------------------------------------------------------

====================================================== \## PROBLEM 2 ---
STUDENT GRADE ANALYSER
======================================================

### 1. CODE QUALITY & CORRECTNESS

✓ Strong subject/assignment modelling.\
✓ Weighted average is correctly implemented for valid inputs.\
✓ Students created automatically when referenced.

**Improvements:**\
- Requires **floating‑point tolerance** for weight sums; exact equality
to 1 is unreliable.\
- `calculate_average` prints an error but returns `0` for no subjects →
returning `None` is clearer.\
- `has_failed_subject()` prints messages inside logical computation
(mixes logic and I/O).

### 2. DEMONSTRATION & ROBUSTNESS

✓ Demonstrates invalid weights, missing assignments, multiple students,
and failure detection.

**Missing robustness tests:**\
- Student with *no subjects at all*.\
- Student failing *multiple* subjects.\
- Floating‑point edge cases (e.g., weights summing to 0.999999).

**Example crash:**\
`add_subject("Alex", "Maths", [(88, "a")])` → TypeError when attempting
score \* weight.

------------------------------------------------------------------------

====================================================== \## PROBLEM 3 ---
MOVIE RECOMMENDATION HELPER
======================================================

### 1. CODE QUALITY & CORRECTNESS

✓ Fully implements add, filter-by-genre, top-rated, and random
recommendation.\
✓ Duplicate titles correctly prevented.\
✓ Case-insensitive genre lookup works.

**Improvements:**\
- No validation of rating *type* or numeric range (0--10).\
- `movie_by_genre` prints results inside helper logic rather than
returning data.\
- `random_good_movie` prints labels even when called programmatically.

### 2. DEMONSTRATION & ROBUSTNESS

✓ Tests duplicates, genre search, top-rated logic, and randomness.

**Missing robustness tests:**\
- Case-insensitive genre variants ("ANIMATED").\
- Out-of-range or non-numeric ratings.\
- Scenario where *no movies* meet the minimum rating.

**Example crash:**\
`movie_by_genre(None)` → `None.lower()` causes AttributeError.

------------------------------------------------------------------------

====================================================== \## PROBLEM 4 ---
EXPENSE SPLITTER ======================================================

### 1. CODE QUALITY & CORRECTNESS

✓ Good validation of amount and participants.\
✓ Total spending and balance logic implemented cleanly.\
✓ Settlement produces correct payer/receiver matching.

**Improvements:**\
- Summary prints zero-value debts ("Florence owes Alice £0.00") ---
could be omitted for clarity.\
- Does not check that payer appears in `split_with`.\
- High‑precision floats accumulate rounding errors without
normalisation.

### 2. DEMONSTRATION & ROBUSTNESS

✓ Extensive testing of invalid cases (negative amounts, missing
participants, decimals).

**Missing robustness tests:**\
- Duplicate participant names.\
- Very large amounts.\
- Non-string types in `split_with`.

**Example crash:**\
`add_expense("Lunch", "Alice", 10, [None])` → failure when printing
summary.

------------------------------------------------------------------------

====================================================== \## PROBLEM 5 ---
BOOLEAN LOGIC EVALUATOR
======================================================

### 1. CODE QUALITY & CORRECTNESS

✓ Correct recursive structure for parentheses.\
✓ Implements operator precedence: NOT → AND → OR.\
✓ Converts tokens correctly for boolean evaluation.

**Issues:**\
- `break_expression` returns None for invalid tokens, yet
`analyse_expression` continues → may produce incorrect final results.\
- Mutating lists in-place during evaluation introduces ordering issues
(NOT chaining).\
- Unbalanced parentheses sometimes yield `None` instead of raising a
clear error.\
- Evaluation sometimes duplicates prints or returns incorrect results.

**Incorrect behaviour examples:**\
- `final_evaluate("true or false")` returns `"False"` (logical
inversion).\
- Nested prints produce duplicate outputs due to repeated evaluation.

### 2. DEMONSTRATION & ROBUSTNESS

✓ Good coverage of valid, invalid, and nested expressions.

**Missing robustness tests:**\
- Double NOT ("not not true").\
- Mixed precedence ("true or false and false").\
- Very deep nesting.\
- Malformed adjacency ("(true)(false)").

**Example crash:**\
Malformed expression such as `["and", True]` → index error in
`analyse_expression`.

------------------------------------------------------------------------

# OVERALL SUMMARY

This is a **strong and clearly structured submission**, demonstrating
good problem understanding and thorough testing across all tasks.

### Key Strengths

✓ Completes all required functionality for all problems\
✓ Good validation and demonstration discipline\
✓ Clean decomposition of logic into functions\
✓ Good error handling in many parts

### Main Recommendations

1.  Introduce **unique book IDs** instead of titles (Problem 1).\
2.  Improve weight-sum robustness and score-type validation (Problem
    2).\
3.  Strengthen type checking and avoid printing in helper functions
    (Problem 3).\
4.  Add more validation to participant lists and payer rules (Problem
    4).\
5.  Make boolean parser more robust: stop on error, avoid mutating lists
    during iteration, and improve precedence handling (Problem 5).

Overall, a well-organised submission with clear logic and strong
demonstrations.
