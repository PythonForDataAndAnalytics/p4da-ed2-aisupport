# SCOPE MAP: Python for Data & Analytics — A Business-Oriented Approach (2nd Ed.)
# Author: Daniel Groner | Publisher: Prospect Press
# Instructional Grounding Design (IGD) Framework
# © Prospect Press
# For authorized educational use only.

---

## About This Scope Map

This Scope Map is a lightweight, structured grounding document designed to orient an AI tutor
to the content and scope of the textbook "Python for Data & Analytics — A Business-Oriented
Approach, 2nd Edition" by Daniel Groner, published by Prospect Press.

---

## How to Use This Scope Map

This Scope Map is intended to be loaded by an AI tutor at the start of a tutoring session.

**Bootstrapping instructions for the AI tutor:**

1. Read this Scope Map in full to establish course-wide scope awareness.
2. Enter learn mode: ground all tutoring responses in the content of this textbook.
   - Stay within the scope of concepts, vocabulary, and syntax introduced up to and
     including the student's current chapter.
   - Do not introduce syntax, functions, or concepts from future chapters or appendices
     unless the student has indicated they have covered them.
   - Use the author's specific terminology and framing where distinctive.
   - Reference named programs and spreadsheet contrasts where relevant.
3. Ask the student which chapter(s) they are focusing on and what specifically they need help with.

---

## Scope Map Structure

Each chapter and appendix section contains Scope Items organized as:

- **Scope Words** — self-resolving technical terms the AI can fully interpret from its own
  training: Keywords, Operators, Functions, Methods
- **Scope Phrases** — author-crafted anchors requiring a short phrase to orient the AI to
  the author's specific framing: Concepts, Patterns, Traps, Tips, Spreadsheet Contrasts

Only populated Scope Item categories appear in each section.

---

## Scope Map Sections


# CHAPTER 1: Introduction to Programming and Python
# Scope Map — p4da-ed2
# © Daniel Groner, Prospect Press.
# Derived from "Python for Data & Analytics, 2nd Ed." — For authorized educational use only.

---

### 1.1 About Programming

- **Concepts:**
  - IPO — all programs follow an Input → Processing → Output pattern
  - Programs contain data and operate on data — using statements in sequence to achieve results
  - RAM vs. persistent storage — data in RAM is fast but lost when program ends; files on disk persist
  - Art vs. science of programming — art is organizing data and logic effectively; science is learning syntax and mechanics

---

### 1.2 Programs as Recipes

- **Concepts:**
  - Cooking-to-programming analogy — ingredients → variables, directions → statements, alternatives → decisions, repetition → loops, parts → functions, cookbook → packages
  - Explicit order of steps — programs must state processing sequence explicitly, unlike spreadsheets which determine calculation order automatically
  - Library / package — a collection of reusable code items, analogous to a cookbook

- **Spreadsheet Contrasts:**
  - Explicit step ordering vs. automatic recalculation — program logic order must be stated by the programmer; spreadsheet calculation engines determine order automatically

---

### 1.3 About Python

- **Concepts:**
  - Python use cases — applications, data science, automation, prototypes, model development
  - Python version history — version 3 is not backward compatible with version 2; this book uses Python 3
  - Python vs. other languages — Python prioritizes developer productivity; C++ prioritizes runtime speed; Java suits large-scale systems; SQL is for relational databases

---

### 1.4 Programming with Python

- **Concepts:**
  - Three ways to run Python — interactive (one line at a time, `>>>` prompt), script (`.py` file run in an IDE), notebook (code cells in Jupyter or Google Colab)
  - Python indentation — groups child statements under a parent statement; used instead of curly braces
  - Implicit data typing — Python determines and tracks variable types automatically
  - Python packages — published via PyPI; enable high productivity for data and analytics tasks

# CHAPTER 2: Variables and Statements
# Scope Map — p4da-ed2
# © Daniel Groner, Prospect Press.
# Derived from "Python for Data & Analytics, 2nd Ed." — For authorized educational use only.

---

### 2.1 About Constants, Variables, and Statements

- **Concepts:**
  - Three Core Ingredients — constants, variables, and statements are the essential building blocks of all programs
  - Multiple Ways to Set Variables — values can come from hard-coded constants, keyboard input, files, or databases

---

### 2.2 Variables

- **Operators:** `=`
- **Functions:** `print()`, `input()`
- **Concepts:**
  - Variables as Named Memory Locations — a variable is a named pointer to a value in memory, not a rigid container
  - Silent Assignment vs. Active Display — assignment executes silently; screen stays blank unless `print()` is called
  - State Mutation — a variable's value can change during program execution
  - The Synchronous Wait — `input()` pauses execution until the user presses Enter
  - Returned Result — `input()` returns the string the user typed, assigned to a variable
- **Traps:**
  - `SyntaxError` — variable name starting with a digit, containing special characters, or matching a keyword
  - `NameError` — case mismatch between variable names (e.g., `Sales` vs. `sales`)
  - `input()` always returns a string — arithmetic without type casting produces errors
- **Spreadsheet Contrasts:**
  - Variables vs. grid cells — both hold values, but Python has a sharper distinction between variables and statements; cell formulas are hidden, Python statements are explicit
  - Variable names vs. cell names — spreadsheet cells have preassigned names (e.g., `A1`); Python programmers invent every variable name

---

### 2.3 Python's Basic Types

- **Functions:** `type()`
- **Concepts:**
  - Type as Operational Permission — a variable's type determines what operations are valid on it
  - Unlimited Integers vs. Bounded Floats — `int` has no size limit; `float` has hardware-imposed boundaries
  - Inexact Floating-Point Architecture — hardware binary representation introduces minor predictable inaccuracies (e.g., `140 - 124.8` → `15.200000000000003`); expected behavior, not a bug
  - Implicit / Dynamic Typing — Python infers types automatically; no explicit type declaration needed
  - Type Invariance as Best Practice — avoid switching a variable's type; use separate variables for separate types
- **Traps:**
  - Float precision surprises — long decimal results are normal floating-point behavior; use `round()` to clean up
  - Comma in integer literals — `1,000` is interpreted as a tuple, not an integer
  - Apostrophe in string literals — `'ABC's inventory'` raises `SyntaxError`; use double quotes instead
- **Spreadsheet Contrasts:**
  - Cell types are largely invisible in spreadsheets; in Python, types are explicit and consequential — especially when getting keyboard input

---

### 2.4 More on Input and Output

- **Functions:** `int()`, `float()`, `str()`
- **Patterns:**
  - Nested casting — `float(input('prompt'))` combines input and type conversion in one statement
  - IPO organization — structure programs as Input → Processing → Output
- **Concepts:**
  - The String-by-Default Constraint — `input()` always returns a string; explicit casting required before math
  - Output Buffering Overrides — `sep=` and `end=` named parameters allow fine-grained control of `print()` output
- **Traps:**
  - `ValueError` — `float()` or `int()` wrapping `input()` when user enters non-numeric text
  - `TypeError` — `+` concatenation mixing string and numeric types without `str()` conversion
- **Spreadsheet Contrasts:**
  - Numeric cell values are inherently available for calculation in spreadsheets; Python `input()` always delivers a string regardless of what the user types — explicit casting always required

---

### 2.5 Mathematical Statements

- **Operators:** `+`, `-`, `*`, `/`, `**`, `%`
- **Concepts:**
  - PEMDAS in Python — operator precedence follows standard algebra conventions
  - Parentheses for Human Readability — adding parentheses beyond what precedence requires improves clarity
- **Traps:**
  - `^` is not exponentiation — Python treats `^` as bitwise XOR; produces silently incorrect results with no error
  - `/` always returns float in Python 3 — `7 / 2` → `3.5`, not `3`
  - `%` is remainder, not percentage — students may confuse with percentage calculation
- **Spreadsheet Contrasts:**
  - Exponentiation symbol fracture — Python uses `**` for exponentiation; spreadsheets use `^`

---

### 2.6 More about Math

- **Operators:** `+=`, `-=`, `*=`, `/=`
- **Functions:** `round()`, `max()`, `min()`, `abs()`, `pow()`
- **Patterns:**
  - Square root via exponentiation — `** .5` computes square root without any library import
- **Concepts:**
  - Managing Precision Noise — `round()` cleans up floating-point display results
  - Augmented Assignment as In-Place Mutation — `+=` and similar operators modify an existing variable in place; cannot initialize a variable
- **Traps:**
  - `NameError` — augmented assignment on uninitialized variable (e.g., `counter += 1` before `counter` is defined)
  - `round()` single-argument returns `int` — `round(3.7)` returns `4`, not `4.0`
  - `ValueError` — `** .5` applied to a negative number
  - `TypeError` — `max()` or `min()` with mixed incompatible types
- **Spreadsheet Contrasts:**
  - In-place modification vs. cell lineage — Excel raises a Circular Reference error if a cell references itself; Python `+=` natively mutates state in place

---

### 2.7 More about Strings

- **Operators:** `+`, `+=`
- **Functions:** `len()`, `format()`
- **Methods:** `.strip()`, `.capitalize()`, `.lower()`, `.upper()`
- **Patterns:**
  - Method chaining — multiple string methods applied left-to-right (e.g., `name.strip().capitalize()`)
  - f-string embedding — variables and format specifiers inside `{}` within an `f'...'` string
- **Concepts:**
  - String Immutability and Silent Returns — string methods return a new string; original variable unchanged unless explicitly reassigned
  - Methods vs. Functions — methods are called using dot notation on a variable; functions are called standalone
- **Traps:**
  - String immutability trap — `name.strip()` alone has no persistent effect; must reassign: `name = name.strip()`
  - Method chaining order matters — order of chained methods affects the result
  - `TypeError` — `+` concatenation of string with non-string type; must use `str()` to convert first
  - `ValueError` — incorrect format specifier string raises error at runtime
- **Spreadsheet Contrasts:**
  - Excel number formatting changes cell display without altering the underlying value; Python `format()` and f-strings produce a new formatted string — the original numeric variable is unchanged

# CHAPTER 3: Decisions
# Scope Map — p4da-ed2
# © Daniel Groner, Prospect Press.
# Derived from "Python for Data & Analytics, 2nd Ed." — For authorized educational use only.

---

### 3.1 About Decisions in Programs

- **Keywords:** `if`
- **Operators:** `<`, `<=`, `>`, `>=`, `==`, `!=`
- **Concepts:**
  - Decision Structures — conditions under which certain statements may or may not execute; first departure from top-to-bottom program flow
  - Logical Expression — an expression that evaluates to `True` or `False` at runtime
  - Colon-and-Indent Pattern — colon followed by indented statements is a required structural pattern in Python
  - Comparison vs. Assignment — `==` tests equality; `=` assigns a value; these are fundamentally different
- **Traps:**
  - `IndentationError` — omitting required indentation beneath `if`
  - `SyntaxError` — missing colon at end of `if` line
  - `SyntaxError` — using `=` instead of `==` in a comparison
  - Arithmetic precedence over comparisons — additions and multiplications are computed before comparison operators

---

### 3.2 Multi-way Decisions

- **Keywords:** `if`, `elif`, `else`
- **Concepts:**
  - Two-way Choice — `if/else` guarantees exactly one of two blocks executes
  - N-way Choice — `elif` extends decision structures to handle any number of alternatives
  - `else` as None of the Above — executes when no prior `if` or `elif` condition was `True`
  - Short-circuit Evaluation — once a `True` condition is found in an `if/elif` chain, no further conditions are evaluated
- **Traps:**
  - Overlapping `elif` conditions — incorrect ordering of conditions captures wrong branch silently
  - `NameError` — variable assigned only inside branches is undefined if all conditions are `False` and no `else` exists
  - `IndentationError` — mixing indentation levels within the same block
- **Spreadsheet Contrasts:**
  - Python `if` vs. spreadsheet `IF` — spreadsheet `IF(condition, true, false)` is a single-line function; Python `if/else` spans multiple lines but logic is often easier to read

---

### 3.3 Nested (Sequential) Decisions

- **Concepts:**
  - Nested Decisions for Multi-Dimensional Logic — nesting handles situations where a primary decision leads to a secondary decision
  - Decision Tree Mapping — a nested `if` structure directly corresponds to a decision tree
  - Indentation Reveals Structure — depth of indentation communicates which decisions are subordinate to which
- **Traps:**
  - `IndentationError` or silent logic errors — misaligned lines in nested structures execute the wrong branch
  - `NameError` — incomplete nesting leaves a required variable unassigned in some branches

---

### 3.4 More about Decisions

- **Keywords:** `and`, `or`, `not`, `match`, `case`
- **Concepts:**
  - Compound Conditions — `and` and `or` combine multiple comparisons into a single logical expression
  - Readability vs. Conciseness — choose the style more readable to others, not just the more concise variation
  - String Equality is Character-by-Character — `==` checks exact character sequence including case; `'e'` ≠ `'E'`
  - Dictionary Order for String Comparisons — `<` and `>` on strings use alphabetical ordering with uppercase before lowercase
  - Terse `if/else` as Expression — compact single-line form `true_value if condition else false_value`; returns a value rather than executing a block
  - `match/case` as Structured Alternative — cleaner syntax than long `if/elif` chains when matching against specific values; `case _:` functions like `else`
- **Traps:**
  - Case sensitivity in string comparisons — `'e'` does not match `'E'`; unexpected branch selection when user enters different case
  - `and` short-circuit evaluation — if first condition is `False`, second condition is never evaluated
  - `SyntaxError` — `match/case` requires Python 3.10+; raises error in earlier versions

# CHAPTER 4: Repetition
# Scope Map — p4da-ed2
# © Daniel Groner, Prospect Press.
# Derived from "Python for Data & Analytics, 2nd Ed." — For authorized educational use only.

---

### 4.1 About Repetition

- **Keywords:** `while`, `for`
- **Concepts:**
  - Repetition vs. Sequential Flow — program flow can move backward to a prior statement; first departure from top-to-bottom execution
  - Two Repetition Keywords — `while` is flexible for user-driven repetition; `for` is concise when the sequence is known
- **Spreadsheet Contrasts:**
  - Repetition vs. copying cells — in a spreadsheet, repeating a calculation means copying a formula down rows; in Python, the logic is written once and the program flow controls its reuse

---

### 4.2 The while Statement

- **Keywords:** `while`
- **Operators:** `+=`, `-=`, `*=`, `/=`
- **Functions:** `print()`
- **Concepts:**
  - The while Flow Cycle — check condition → if True execute body → return to condition → repeat; if False skip body
  - Loop Control Variable Three-Part Rule — every `while` loop requires (1) initialization before, (2) testing in condition, (3) updating inside body
  - Cumulation Pattern — tracking variable initialized to zero before loop accumulates values across iterations
  - Maximum/Minimum Tracking — initialize to first value, use `if` inside loop to update when new extreme found
  - `bool` Type — `True` and `False` are Python boolean literals; comparison expressions evaluate to and can be assigned as `True`/`False`
  - Case Sensitivity in String Loop Conditions — `'y'` does not match `'Y'`; use `.lower()` to make condition case-insensitive
  - Statements Outside the Loop Execute Once — headers and initialization placed inside the loop cause unnecessary repetition
- **Traps:**
  - Infinite loop — loop control variable never updated inside body; condition stays `True` forever
  - `NameError` — cumulation variable not initialized before loop
  - Off-by-one — using `<` vs. `<=` causes last iteration to be skipped or loop to run one extra time
  - Case sensitivity trap — uppercase entry when loop tests for lowercase terminates or continues loop unexpectedly
  - `NameError` — first `input()` call missing before loop; control variable undefined when condition first evaluated

---

### 4.3 The for Statement, with range() Function

- **Keywords:** `for`, `in`
- **Functions:** `range()`
- **Concepts:**
  - `for`/`range()` Dialogue — `for` asks `range()` for values one at a time; `range()` signals when exhausted; manages initialization, testing, and updating automatically
  - Right-Open Boundary of `range()` — `range(1, n+1)` is the standard pattern to include `n` as the last value
  - `for` Fully Handles the Loop Target Variable — no need to initialize before or update inside the body
  - `range(count)` Starts at 0 — single-argument `range()` generates 0 to count-1
- **Traps:**
  - `range()` right-open boundary confusion — `range(1, 5)` generates 1–4, not 1–5
  - `TypeError` — passing a `float` argument to `range()`
  - Modifying loop target variable inside body has no effect — `for` overwrites it on each pass

---

### 4.4 Using while vs. for

- **Concepts:**
  - `for` is More Concise — combines initialization, condition, and update into one line
  - `while` for User-Driven Repetition — natural fit when user decides during execution whether to continue
  - Same Problem, Two Solutions — understanding when each is preferred is a design skill

---

### 4.5 Infinite Loops

- **Concepts:**
  - Infinite Loop as Logic Bug — usually caused by forgetting to update the loop control variable inside the body
  - Diagnosis Strategy — inspect variables in the `while` condition; verify they are initialized and changed inside the loop
- **Traps:**
  - Program freezes/hangs — visible symptom of infinite loop; use `Control+C` to interrupt
  - Missing increment is the most common cause — forgetting `i += 1` at bottom of `while` body

---

### 4.6 Adding Validation

- **Concepts:**
  - Two Validation Approaches — `if/else` inside loop checks each iteration; separate validation `while` loop re-prompts until valid input received
  - Validation Loop as a Guard — program cannot proceed past validation `while` until valid input is received
  - Nested while for Multiple Variables — each input requiring validation gets its own validation `while` loop
- **Traps:**
  - Boundary condition matters — `while height <= 0:` rejects zero and negatives; `while height < 0:` incorrectly allows zero
  - `ValueError` — non-numeric input crashes even a validation loop; Appendix D handles this case
  - Infinite validation loop — wrong validation condition causes valid input to never satisfy it

---

### 4.7 About break and continue

- **Keywords:** `break`, `continue`
- **Concepts:**
  - `break` Exits the Loop Entirely — jumps to first statement after the loop; no further iterations occur
  - `continue` Skips to the Next Iteration — remaining statements in current iteration skipped; flow returns to condition
  - Preferred Alternatives — `if/else` structures or restructured `while` conditions are almost always clearer than `break` or `continue`
- **Traps:**
  - `break` inside nested loops exits only the innermost loop — students may expect it to exit all loops
  - `continue` does not exit the loop — skips to next iteration only; students sometimes confuse it with `break`

# CHAPTER 5: Defining Functions
# Scope Map — p4da-ed2
# © Daniel Groner, Prospect Press.
# Derived from "Python for Data & Analytics, 2nd Ed." — For authorized educational use only.

---

### 5.1 Introduction to Functions

- **Keywords:** `def`, `return`
- **Concepts:**
  - Functions as Program Organizers — functions organize programs into coherent units of logic, the way paragraphs organize an essay
  - Defining vs. Calling — writing a `def` block does not execute the function; it runs only when explicitly called
  - Local Variables — variables created inside a function exist only during that function's execution
  - "Quiet" Functions — well-designed functions accept inputs via parameters and provide results via `return`; display logic kept separate
  - Two Possible Outcomes — a function either returns a result or raises an exception
- **Traps:**
  - Defining without calling — a `def` block never called produces no output and no error
  - `NameError` — calling a function before its `def` block appears in the file
  - Forgetting `return` — function silently returns `None`; causes errors in subsequent calculations
  - `NameError` — attempting to use a local variable from outside the function
- **Spreadsheet Contrasts:**
  - Spreadsheet functions vs. Python functions — both accept arguments and return results; Python uniquely allows programmers to define their own functions directly in code

---

### 5.2 Multiple Parameters

- **Concepts:**
  - Argument Order Matters — position of each argument determines which parameter receives it; reversed order causes `TypeError` or silently wrong results
  - Constants as Arguments — passing constants directly (e.g., tax rate `.075`) is common for fixed values
  - Function Design — deciding what functions to have and what each function's inputs, processing, and output are; no single correct answer
- **Traps:**
  - `TypeError` — wrong argument order or float passed where int is required
  - `TypeError` — wrong number of arguments; too few or too many raises `TypeError`

---

### 5.3 More Function Features

- **Concepts:**
  - Named Parameters for Defaults with Flexibility — named parameters provide sensible defaults while allowing caller to override when needed
  - Multiple Returns as Related Outputs — returning two or more related results together in a single `return` statement
  - Tuple Unpacking — `a, b = functionName(...)` unpacks returned values; receiving variable count must match returned value count
- **Traps:**
  - `SyntaxError` — named parameters declared before positional parameters in signature
  - `SyntaxError` — named parameter overrides placed before positional arguments in call
  - `ValueError` — mismatched unpacking; receiving variable count does not match returned value count

---

### 5.4 Functions and the Console: Input and Output

- **Concepts:**
  - Two Ways a Function Provides Output — `return` results to caller, or display to screen via `print()`; different mechanisms that can be combined
  - Two Ways a Function Receives Input — parameters in signature, or keyboard `input()` inside body; can be combined
  - IPO Separation Pattern — separate functions for input, processing, and output make each part easier to understand and test independently
  - `None` Return Value — function with bare `return` or no `return` returns `None`; valid to assign but causes `TypeError` if used in arithmetic
- **Traps:**
  - `TypeError` — `None` result inadvertently used in arithmetic
  - `TypeError` — arguments passed to a function defined with empty parameter list

---

### 5.5 A Function Calling Another Function

- **Concepts:**
  - `main()` as Program Organizer — groups highest-level control flow; typically the only non-indented statement that executes at the top level
  - Function Call Chains — Python tracks the full call sequence and unwinds it as each function completes; programmer does not manage this explicitly
- **Traps:**
  - Forgetting to call `main()` — defining `main()` without a `main()` call at end of file produces no output

---

### 5.6 Some Further Design Points for Functions

- **Concepts:**
  - Self-Contained Functions — function behavior should depend only on input parameters, not on variables defined outside it
  - Global Variables as Anti-Pattern — relying on global variables creates hidden dependencies; makes programs harder to maintain
  - Function Size Guidelines — no hard rule; a function longer than a screenful may need splitting
- **Traps:**
  - Global variable side effects — function reading or modifying global variable produces behavior dependent on outside program state
  - Naming collision — local variable with same name as global shadows the global within the function

---

### 5.7 Combining Concepts: Functions and Decisions

- **Concepts:**
  - Functions as Logic Containers — functions can contain any combination of decisions, repetition, and other statements
  - Discount Logic Pattern — placing conditional business rules inside the calculating function keeps decision and calculation together; calling code remains simple
- **Traps:**
  - `NameError` — `if/else` inside function assigns variable in some branches but not others; unassigned branch reached
  - Early `return` inside a branch — function returns before all intended code paths are reached

# CHAPTER 6: Lists
# Scope Map — p4da-ed2
# © Daniel Groner, Prospect Press.
# Derived from "Python for Data & Analytics, 2nd Ed." — For authorized educational use only.

---

### 6.1 About Lists

- **Concepts:**
  - Lists as Ordered Sets — a list keeps track of an ordered set of related items; order is preserved and meaningful
  - Lists as a Key Building Block — lists become essential as programs grow to track multiple related values
- **Spreadsheet Contrasts:**
  - Lists vs. cell ranges — a Python list is similar to a spreadsheet cell range (e.g., `A1:A10`); Python requires a programmer-chosen name where spreadsheets use cell coordinates

---

### 6.2 Creating Lists

- **Functions:** `len()`, `float()`
- **Methods:** `.append()`
- **Concepts:**
  - Two Ways to Create a List — define all items at once with `[]`; or create empty list and add items with `.append()` when items are not known ahead of time
  - Index Zero Convention — Python lists are zero-indexed; first item is at index `0`, not `1`
  - Negative Indexing — `list[-1]` is always the last item regardless of list length
  - Parallel Lists — multiple equal-length lists where corresponding items at the same index are related
  - Methods vs. Functions — methods are connected to a variable with a period; each type has methods suitable for that type
- **Traps:**
  - `IndexError` — accessing an index that doesn't exist
  - Off-by-one from zero indexing — `colors[1]` gives the second item, not the first
  - `NameError` — calling `.append()` before the list variable is created
- **Spreadsheet Contrasts:**
  - Named lists vs. cell ranges — Python requires explicit iteration and functions like `len()`, `min()`, `max()` to interrogate a list; spreadsheet ranges are implicitly known

---

### 6.3 Iterating over a List to Get a List's Items

- **Keywords:** `for`, `in`
- **Functions:** `len()`
- **Concepts:**
  - Two Iteration Patterns — index-based `for i in range(len(alist)):` when index needed; simplified `for value in alist:` when only item value needed
- **Traps:**
  - Empty list with `for value in alist:` — loop body never executes; silent, no error
  - `ZeroDivisionError` — dividing by `len(alist)` when list is empty

---

### 6.4 Getting Part of a List with Slicing

- **Concepts:**
  - Slicing is Right-Open — like `range()`, slicing goes up to but not including the end index
  - Slicing Returns a New List — modifying the slice does not affect the original list
  - Growing Average Pattern — `alist[0:i+1]` grows from one item to full list as `i` increases
- **Traps:**
  - Slice out-of-range does not error — `alist[0:100]` on a 5-item list returns the full list silently
  - Right-open boundary confusion — `alist[1:3]` returns 2 items (indexes 1 and 2), not 3

---

### 6.5 Asking Questions of a List

- **Keywords:** `in`, `not in`
- **Functions:** `len()`, `min()`, `max()`
- **Concepts:**
  - List Interrogation Functions — `len()`, `min()`, `max()` treat the entire list as a unit; no explicit loop needed
  - `in` as a Boolean Expression — `value in alist` evaluates to `True` or `False`; usable in `if`, `while`, or `print()`
- **Traps:**
  - `ValueError` — `min()` or `max()` called on empty list
  - `TypeError` — `min()` or `max()` on mixed-type list
  - `in` with float precision — exact equality used for membership testing; float precision may cause unexpected misses

---

### 6.6 Maintaining a List

- **Keywords:** `del`
- **Methods:** `.append()`, `.insert()`, `.extend()`, `.remove()`, `.pop()`, `.clear()`, `.copy()`
- **Concepts:**
  - Mutability of Lists — list items can be changed, added, or removed after creation
  - List Aliasing vs. Copying — `b = a` makes both variables point to the same list; use `.copy()` for an independent copy
  - Backward Deletion Pattern — when deleting items inside a loop, iterate backward to avoid index shifting errors
  - `extend()` vs. `append()` — `.append(otherList)` adds entire list as single nested item; `.extend(otherList)` adds each item individually
- **Traps:**
  - List aliasing trap — `b = a` then modifying `a[i]` silently changes `b[i]`; use `b = a.copy()`
  - `ValueError` — `.remove()` called on value not in list
  - Forward deletion index shift — deleting while iterating forward skips the item after the deleted one
  - `IndexError` — `.pop()` called on empty list

---

### 6.7 Ordering a List: sorted(), sort(), reverse()

- **Functions:** `sorted()`
- **Methods:** `.sort()`, `.reverse()`
- **Concepts:**
  - `sorted()` vs. `.sort()` — `sorted()` returns a new list, original unchanged; `.sort()` modifies in place and returns `None`
  - In-place methods return `None` — assigning `.sort()` or `.reverse()` result to a variable gives `None`, not the sorted list
- **Traps:**
  - `newList = alist.sort()` gives `None` — use `sorted(alist)` if a new sorted list is needed
  - `TypeError` — `.sort()` on mixed-type list; cannot compare strings and numbers

---

### 6.8 Representing a Table in a List

- **Concepts:**
  - Table as List of Lists — main list points to child lists; each child list represents a row
  - Nested Loops for Table Traversal — outer loop iterates over rows; inner loop iterates over cells within each row
  - pandas Preview — Chapter 10 introduces `DataFrame` as a more powerful approach for tabular data
- **Traps:**
  - Two-index access required — `matrix[0]` returns a row; `matrix[0][1]` needed to access a specific cell
  - Appending to child lists — `result[0].append(i)` vs. `result.append(i)` target different levels of the structure
- **Spreadsheet Contrasts:**
  - Cell ranges and list of lists — spreadsheets are inherently tabular; Python can represent tables as list of lists, and also higher-order dimensions (cubes); Python data structures like dictionaries and DataFrames offer greater flexibility than spreadsheet tables

---

### 6.9 About Tuples—Unchangeable Lists

- **Concepts:**
  - Tuples as Immutable Lists — like lists but items cannot be changed after creation; parentheses `()` instead of `[]`
  - Tuples as Constants — using a tuple signals that the data is not intended to change
- **Traps:**
  - `TypeError` — assigning to a tuple item (`tupleName[0] = 'new'`)
  - `AttributeError` — calling `.append()` or `.sort()` on a tuple

# CHAPTER 7: Reading and Writing Files
# Scope Map — p4da-ed2
# © Daniel Groner, Prospect Press.
# Derived from "Python for Data & Analytics, 2nd Ed." — For authorized educational use only.

---

### 7.1 About Files

- **Concepts:**
  - Text files vs. binary files — text files can be viewed in a text editor; binary files are beyond the scope of this book
  - Files as I/O alternative — files are a practical alternative to keyboard input and screen output for larger datasets

---

### 7.2 Reading a File's Line

- **Functions:** `open()`
- **Methods:** `.readline()`, `.rstrip()`, `.close()`
- **Concepts:**
  - File variable — the Python object set by `open()` that connects the program to the file; used subsequently with methods
  - `open()` connects, `readline()` reads — `open()` establishes the connection but does not read data
  - Trailing newline convention — `readline()` includes `\n` at end of returned string; `rstrip('\n')` removes it
  - Four-step file reading pattern — open, readline, rstrip, close
- **Traps:**
  - `FileNotFoundError` — `open()` raises this if the specified file does not exist

---

### 7.3 Reading a File's Lines with Repetition

- **Keywords:** `for`, `while`
- **Methods:** `.readline()`, `.rstrip()`, `.strip()`
- **Functions:** `float()`
- **Patterns:**
  - `while` loop with `readline()` — priming read before loop; `while line != '':` as condition; subsequent read inside body
  - `for` loop over file variable — `for line in f:` iterates over each line; more concise than `while`; preferred approach
  - Skip header line — call `f.readline()` once before the loop to discard the header without processing it
- **Concepts:**
  - Empty string as end-of-file sentinel — `readline()` returns `''` when all lines are exhausted; this is the `while` loop termination signal
  - Accumulator pattern applied to file reading — running total and count accumulated inside file-reading loop
- **Traps:**
  - Infinite loop — forgetting the priming read before `while` loop, or forgetting subsequent read inside loop body
  - `ZeroDivisionError` — dividing by count variable that remains 0 when file is empty

---

### 7.4 Parsing a File's Fields

- **Methods:** `.split()`
- **Functions:** `int()`, `float()`
- **Patterns:**
  - Parse and convert pattern — `split(',')` to divide a line into fields; `int()` and `float()` to convert string fields to numeric types
  - `parseLine()` function — encapsulates splitting and type conversion; returns multiple values unpacked by caller
- **Concepts:**
  - Parsing — dividing data into parts by splitting a file line into fields and converting to appropriate types
  - Whitespace as delimiter — `split()` with no arguments splits on any whitespace (space, tab, newline)
- **Traps:**
  - `IndexError` — accessing `fields[n]` when split result has fewer elements than expected (malformed line)
  - `ValueError` — `int()` or `float()` called on a field containing non-numeric string data
- **Spreadsheet Contrasts:**
  - Spreadsheet import vs. file read — spreadsheets import CSV data into cells automatically; Python requires explicit `open()`, `readline()`/`for`, `split()`, and type conversion to read and parse a data file

---

### 7.5 Writing a File

- **Functions:** `open()`, `print()`
- **Methods:** `.close()`
- **Concepts:**
  - Writing reuses `print()` — `file=fout` named parameter redirects output to a file instead of the screen
  - `open()` with `'w'` is destructive — creates the file or silently overwrites it if it already exists
  - Header record written once before the loop — not inside the loop body
  - Simultaneous read and write — a program can have both an input and output file variable open at the same time
- **Traps:**
  - `open(filename, 'w')` silently overwrites existing file with no warning — data loss if wrong filename used

---

### 7.6 Handling Errors with Exceptions

- **Keywords:** `try`, `except`
- **Concepts:**
  - Exception — an error that occurs during program flow
  - `except` block as backup plan — runs only if the `try` block raises an error; skipped if no error occurs
  - File activity belongs inside `try` — subsequent reads after `open()` should also be inside the `try` block to catch any file error
- **Traps:**
  - `ValueError` — `float()` or `int()` called on non-numeric string input
  - `FileNotFoundError` — `open()` called on a file that does not exist; caught by `try`/`except`

# CHAPTER 8: Strings in Detail
# Scope Map — p4da-ed2
# © Daniel Groner, Prospect Press.
# Derived from "Python for Data & Analytics, 2nd Ed." — For authorized educational use only.

---

### 8.1 String Basics Recap

- **Operators:** `+`, `+=`, `==`, `!=`, `<`, `>`, `<=`, `>=`
- **Functions:** `len()`, `int()`, `float()`, `str()`, `ord()`, `chr()`, `type()`
- **Concepts:**
  - String Immutability — square brackets can only get a character, not set one; `s[0] = 'h'` raises `TypeError`
  - String Reassignment vs. Mutation — a string variable can be reassigned to a different string even though the string itself cannot be mutated in place
  - ASCII-based String Ordering — string comparisons use ASCII character values; uppercase letters have lower numeric values than lowercase
  - `ord()` and `chr()` bridge — convert between characters and their numeric ASCII representations
- **Traps:**
  - `TypeError` — attempting to assign to a string index (e.g., `s[0] = 'h'`)
- **Spreadsheet Contrasts:**
  - Spreadsheet text vs. Python strings — spreadsheet cell text is similar to string literals; Python string methods are analogous to spreadsheet text functions and often more concise

---

### 8.2 Substrings (Slicing)

- **Concepts:**
  - Slicing is right-open — `s[i:j]` returns characters from `i` up to but not including `j`
  - Slicing does not alter the original string — creates a new string
  - Same slicing syntax as lists — introduced in Chapter 6; applies identically to strings
- **Traps:**
  - Off-by-one errors — forgetting the stop index is exclusive leads to missing the last intended character
  - Hardcoded slice positions — assume fixed-format string; different formats yield wrong results

---

### 8.3 Searching Parts of Strings

- **Keywords:** `in`, `not in`
- **Methods:** `.startswith()`, `.endswith()`, `.find()`, `.rfind()`, `.count()`, `.index()`, `.rindex()`
- **Concepts:**
  - Search method return types — section 8.3 methods return `int` (index or `-1`) or `bool`; not a string
  - `find()` vs. `index()` — `find()` returns `-1` on failure (safe); `index()` raises an exception on failure (use when absence is an error)
  - `in` and `not in` as concise membership tests — use when only a boolean result is needed
- **Traps:**
  - `find()` returning `-1` used as index — `name[-1]` accesses the last character instead of signaling failure; always check return value
  - `index()` raises exception if substring not found — use `find()` when absence is a valid condition
  - Assuming a space exists in a name string before checking `find()` result for `-1`

---

### 8.4 Methods That Return String Variations

- **Methods:** `.strip()`, `.lstrip()`, `.rstrip()`, `.upper()`, `.lower()`, `.swapcase()`, `.capitalize()`, `.title()`, `.center()`, `.ljust()`, `.rjust()`, `.replace()`, `.format()`, `.expandtabs()`, `.zfill()`
- **Concepts:**
  - All variation methods return a new string — the original string is unchanged
  - Reassignment required to update — `s = s.lower()` is required; `s.lower()` alone leaves `s` unchanged
  - Method chaining — each string method returns a string, which can immediately have another method called on it
  - `replace(old, '')` deletes — replacing with empty string effectively removes all occurrences of `old`
- **Traps:**
  - Silent no-op trap — calling `s.lower()` without reassigning; `s` is unchanged, no error raised

---

### 8.5 Checking Strings

- **Functions:** `any()`, `map()`
- **Methods:** `.isalnum()`, `.isalpha()`, `.isascii()`, `.isdecimal()`, `.isdigit()`, `.isidentifier()`, `.islower()`, `.isnumeric()`, `.isprintable()`, `.isspace()`, `.istitle()`, `.isupper()`
- **Concepts:**
  - `is...()` methods check all characters — return `True` only if every character meets the condition
  - `any(map(str.methodname, s))` pattern — concise way to check if at least one character meets a condition
  - String checking methods as input validation tools — primary use case for `is...()` methods
- **Traps:**
  - `isdigit()` on full string — returns `True` only if all characters are digits; confusing this with "contains a digit" is a common logic error
  - Empty string returns `False` for most `is...()` methods — guard against empty input before calling

---

### 8.6 Splitting Strings

- **Methods:** `.split()`, `.splitlines()`, `.partition()`, `.rpartition()`, `.join()`
- **Concepts:**
  - `split()` returns a list of strings — not a string
  - Direct unpacking of `split()` result — when field count is known, results unpacked directly into variables
  - `join()` is the inverse of `split()` — assembles a list of strings into a single string with a specified separator
  - `split()`/`join()` idiom — concise pattern for normalizing whitespace in a string
- **Traps:**
  - `ValueError` — unpacking `split()` result when field count does not match number of receiving variables
  - `ValueError` or `IndexError` — `int()` or `float()` on `split()` result when fewer elements than expected

---

### 8.7 An Example with Strings, Lists, and a File

- **Methods:** `.startswith()`, `.lower()`, `.strip()`
- **Patterns:**
  - Load file into list of lists — open file, read lines, `split(',')`, `append()` sublist for each record
  - Normalize before matching — apply `.strip().lower()` to user input and `.lower()` to stored data for case-insensitive comparison
  - Sentinel-controlled query loop — continue prompting for searches until user enters `'quit'`
  - Skip comment lines — `if line[0] != '#'` filters lines starting with `#` during file read
- **Concepts:**
  - Integration of strings, lists, and file I/O — combining all three in a single program to build a searchable data store

# CHAPTER 9: Dictionaries and Sets
# Scope Map — p4da-ed2
# © Daniel Groner, Prospect Press.
# Derived from "Python for Data & Analytics, 2nd Ed." — For authorized educational use only.

---

### 9.1 About Dictionaries

- **Concepts:**
  - Dictionary as key/value pairs — stores a collection of keys each associated with a value; keys are not limited to integers
  - Unique keys — each key must be unique within a given dictionary
  - Dictionaries vs. parallel lists — faster lookup; tighter data organization in one variable rather than two
  - Dictionary of dictionaries — values can be any Python type including other dictionaries; models hierarchical/record-style data
- **Spreadsheet Contrasts:**
  - Labeling cells vs. dictionary keys — spreadsheet text labels adjacent values similarly to dictionary key/value pairs; Python dictionary values are not limited to simple types and can model complex layouts spreadsheets cannot easily represent

---

### 9.2 Creating Dictionaries

- **Functions:** `type()`
- **Concepts:**
  - Two creation paths — literal with initial values, or empty dictionary populated dynamically
  - Empty dictionary uses `{}` — same syntax as empty set is NOT used; `{}` creates a dictionary, not a set

---

### 9.3 Finding Data in a Dictionary

- **Keywords:** `in`, `not in`
- **Concepts:**
  - Dictionary lookup syntax — `adict[key]` similar to list index access but key is not limited to integers
  - Safe lookup pattern — use `if key in adict:` guard before accessing to prevent `KeyError`
- **Traps:**
  - `KeyError` — accessing `adict[key]` when the key does not exist; analogous to `IndexError` for out-of-range list index

---

### 9.4 Using for to Access Dictionary Items

- **Keywords:** `for`
- **Methods:** `.keys()`, `.values()`, `.items()`
- **Functions:** `len()`
- **Concepts:**
  - Three `for` variations — iterate over keys, values, or key/value pairs depending on what is needed
  - `items()` unpacking — `for key, value in dict.items():` unpacks each `(key, value)` tuple directly into two loop variables
  - `len()` counts keys only — consistent with the primary unit of a dictionary being its key/value pairs

---

### 9.5 Storing Data Fields in Dictionaries

- **Concepts:**
  - Named fields via inner dictionary — field names act as keys; fields accessed by name rather than by index number
  - Dictionary of dictionaries for records — outer key (e.g., email) points to inner dictionary of named fields (e.g., phone, first, last)

---

### 9.6 Maintaining Dictionaries

- **Keywords:** `del`
- **Methods:** `.update()`
- **Concepts:**
  - Add or update with same syntax — `dictionary[key] = value` adds when key is new, updates when key already exists
  - `update()` as in-place merge — conflicting keys resolved in favor of the argument dictionary
- **Traps:**
  - `KeyError` — `del dictionary[key]` when key is not in the dictionary; use `in` guard before deleting

---

### 9.7 Sets

- **Operators:** `|`, `&`, `-`
- **Functions:** `set()`
- **Methods:** `.add()`, `.remove()`, `.symmetric_difference()`
- **Concepts:**
  - Set stores distinct items — duplicates automatically disregarded; duplicate adds silently ignored
  - Sets do not preserve insertion order — items stored in Python's internal order for efficiency; use list or tuple if order matters
  - `set()` for empty set — `{}` creates an empty dictionary, not a set
- **Traps:**
  - `{}` creates empty dictionary not empty set — use `set()` to create an empty set
  - `KeyError` — `set.remove(item)` when item is not in set; use `in` guard before removing

---

### 9.8 An Example with Dictionaries and Files

- **Patterns:**
  - Dictionary of dictionaries from file — load records into outer dict keyed by unique ID; sub-dict holds fields and accumulator initialized to `0`
  - Accumulate into sub-dictionary field — `adict[id]['field'] += value` pattern for running totals keyed by ID
  - Join data from multiple files by shared key — dictionary enables in-memory join across two files

---

### 9.9 About the Hashable Type

- **Concepts:**
  - Hashable types — `str`, `int`, `tuple` are hashable and valid as dictionary keys or set items
  - Lists are not hashable — mutable; cannot be used as dictionary keys or set items
  - Tuples are hashable — immutable; valid as multi-part dictionary keys
- **Traps:**
  - `TypeError: unhashable type: 'list'` — raised when attempting to use a list as a dictionary key or set item

# CHAPTER 10: pandas DataFrames and Series
# Scope Map — p4da-ed2
# © Daniel Groner, Prospect Press.
# Derived from "Python for Data & Analytics, 2nd Ed." — For authorized educational use only.

---

### 10.1 About pandas DataFrames and Series

- **Keywords:** `import`, `as`
- **Concepts:**
  - pandas fills Python's table gap — Python has no built-in table structure; pandas provides `DataFrame` and `Series`
  - DataFrame structure — matrix of data with named columns and named rows; row names form the index; columns generally share one type
  - Series structure — a named list of items; like a one-column DataFrame; some DataFrame methods return a Series
  - NumPy numeric types — pandas uses `int64` and `float64` for efficiency; `object` dtype indicates non-numeric (typically string) columns
- **Spreadsheet Contrasts:**
  - DataFrames vs. spreadsheet sheets — both are tabular; spreadsheet columns are alphabetically named, rows numerically named; DataFrames allow meaningful row and column names; DataFrames enforce one type per column while spreadsheets allow any type in any cell

---

### 10.2 Creating DataFrames

- **Functions:** `pd.DataFrame()`, `pd.read_csv()`
- **Concepts:**
  - Two creation paths — define data in code using a dictionary of lists; or load from a file using `read_csv()`
  - `read_csv()` handles many formats — not limited to comma-separated; delimiter, index column, and comment character are all configurable
  - Hard-coded DataFrames suitable for small fixed reference tables — in practice data usually loaded from outside the program

---

### 10.3 Getting Information about DataFrame Data

- **Functions:** `len()`
- **Methods:** `.head()`, `.tail()`, `.info()`
- **Concepts:**
  - `head()` and `tail()` confirm load — primary tools for verifying a DataFrame loaded correctly
  - `info()` reveals data quality — columns with fewer non-null values than total rows have missing data
  - `df.shape` property — returns `(rows, columns)` tuple; `df.shape[0]` for row count, `df.shape[1]` for column count
  - `pd.options.display.max_rows` — controls how many rows are displayed in a notebook

---

### 10.4 Getting Data: Columns, Rows, and Cells

- **Methods:** `.tolist()`, `.loc[]`, `.iloc[]`
- **Concepts:**
  - Single vs. double brackets for columns — `df['col']` returns a Series; `df[['col1', 'col2']]` returns a DataFrame; distinction matters for downstream operations
  - `.loc[]` vs. `.iloc[]` — `.loc[]` uses named row access; `.iloc[]` uses integer-position access; analogous to dict lookup vs. list index
  - Guard before `.loc[]` access — `if symbol in df.index:` prevents `KeyError` on missing row names
- **Traps:**
  - `KeyError` — `df.loc['rowname']` with row name not in index; use `if key in df.index:` to guard
  - `TypeError` — passing string argument to `iloc[]`; `iloc` requires integer positions only
  - Single vs. double bracket confusion — `df['col']` returns Series; `df[['col']]` returns DataFrame; mixing causes type errors downstream

---

### 10.5 Getting Data: Sorting, Filtering, Slicing, Looping

- **Operators:** `&`, `|`, `~`
- **Methods:** `.sort_values()`, `.iterrows()`, `.str.contains()`, `.str.startswith()`, `.str.endswith()`
- **Concepts:**
  - Sorting returns new DataFrame by default — `inplace=True` replicates spreadsheet in-place sort behavior
  - Filter as Boolean Series — filter condition first produces a Boolean Series (one `True`/`False` per row), then selects matching rows
  - pandas filter operators — use `&`, `|`, `~` instead of Python's `and`, `or`, `not`; parentheses required around each sub-condition
  - `iterrows()` for row-by-row looping — less concise and less efficient than vectorized operations; use when row-by-row processing is genuinely needed
- **Traps:**
  - Operator precedence error — missing parentheses around filter sub-conditions causes error; correct form is `df[(df.col == 'A') | (df.col == 'B')]`
  - `ValueError` — using Python `and`/`or`/`not` keywords in DataFrame filter expressions
- **Spreadsheet Contrasts:**
  - Sorting — spreadsheets sort in place replacing prior order; pandas `sort_values()` returns a new DataFrame by default, leaving the original unchanged
  - Filtering — both support filtering rows; DataFrames provide more flexibility in composing multi-condition filters

---

### 10.6 Missing Values

- **Methods:** `.isna()`, `.notna()`, `.info()`
- **Concepts:**
  - `NaN` — NumPy value representing a missing numeric value in pandas; `None` used for missing values in non-numeric columns
  - Integer column upcasting — when a previously all-integer column gains a `NaN`, pandas may upcast it to `float64`
  - `isna()` and `notna()` — primary tools for identifying and filtering missing data
- **Spreadsheet Contrasts:**
  - Missing values — spreadsheets represent missing data as empty cells; pandas uses `NaN` to mark missing numeric cells; both are handled automatically by aggregation functions

---

### 10.7 Maintaining DataFrame Data

- **Functions:** `pd.concat()`, `pd.DataFrame()`
- **Methods:** `.drop()`, `.at[]`
- **Concepts:**
  - Add column with `df['newcol'] = list` — same syntax as adding a dictionary key; overwrites if column exists, adds if not
  - `concat()` for appending rows — always returns a new DataFrame; requires reassignment; no `inplace` parameter
  - `drop()` with `inplace=True` — modifies DataFrame directly; without `inplace` returns a new DataFrame
  - `at[]` for precise cell update — sets a single cell value by row name and column name

---

### 10.8 Joining Two DataFrames

- **Methods:** `.join()`
- **Concepts:**
  - `join()` matches on index values — both DataFrames share row names as the join key
  - `join()` returns a new DataFrame — does not modify the original
  - `how` parameter controls row inclusion — `'left'` (default), `'right'`, `'outer'`, `'inner'`; unmatched rows produce `NaN`

# APPENDIX B: Importing Packages and Modules
# Scope Map — p4da-ed2
# © Daniel Groner, Prospect Press.
# Derived from "Python for Data & Analytics, 2nd Ed." — For authorized educational use only.

---

### B.1 About Modules, Packages, and Importing

- **Keywords:** `import`, `from`
- **Concepts:**
  - Package vs. module — a package is a third-party library that must be installed and imported; a module ships with Python but must be explicitly imported
  - `import` works in both scripts and notebooks — same syntax in `.py` files, Jupyter Notebook, and Google Colab

---

### B.2 import

- **Keywords:** `import`, `as`
- **Concepts:**
  - Dot-prefix access — after `import modulename`, all items accessible but must be prefixed with module name or alias
  - `as` alias for shorter prefix — a convenience, not a requirement; `import pandas as pd` is the standard pandas alias used throughout the book

---

### B.3 Third-Party Packages

- **Concepts:**
  - Install before import — third-party packages must be installed before they can be imported; installation is separate from importing
  - `pip install` for installation — from Command Prompt (Windows) or Terminal (Mac); prefix with `!` inside a notebook cell
  - Anaconda and Google Colab pre-install common packages — many commonly used packages available without manual installation

---

### B.4 from/import

- **Keywords:** `from`, `import`
- **Concepts:**
  - `from/import` loads specific items only — items used without a prefix; key distinction from plain `import`
  - Use when only a few specific items needed — avoids loading entire module when only selected items are required

---

### B.5 Multifile Applications

- **Keywords:** `import`
- **Concepts:**
  - Same `import` syntax for programmer-written files — import a `.py` file by filename without the extension; same syntax as importing standard modules
  - Dot-prefix for cross-file function calls — `filename.functionname(args)` uses the imported file's name as prefix
  - Multi-file organization for larger programs — split code into multiple files as programs grow
# APPENDIX C: Formatting
# Scope Map — p4da-ed2
# © Daniel Groner, Prospect Press.
# Derived from "Python for Data & Analytics, 2nd Ed." — For authorized educational use only.

---

### C.1 About Formatting

- **Functions:** `round()`
- **Concepts:**
  - Two formatting approaches — `format()` function and f-strings; both use the same format spec syntax
  - `round()` vs. `format()` — `round()` is simplest for limiting decimals but does not guarantee trailing zeros; `format()` used when exact decimal place control is needed

---

### C.2 Python format() Function

- **Functions:** `format()`
- **Concepts:**
  - `format()` always returns a string — even when formatting a numeric value
  - Format spec elements — `width`, `.precision`, `,` for thousands separator, `f`/`d`/`s` type suffix, alignment (`<`, `^`, `>`), sign (`+`), fill character
  - Width padding for column alignment — using consistent width spec across multiple `print()` calls aligns numbers in a column
  - Omitting `f` type suffix produces scientific notation

---

### C.3 Python f-strings

- **Concepts:**
  - f-string as formatted string literal — text and embedded expressions combined in one concise string; prefixed with `f`; variables or expressions inside `{ }`
  - Shared format spec syntax — format spec inside f-string `{ }` is identical to `format()` function spec; learning one applies to both
  - Variable width in f-string — format spec itself can contain a variable (e.g., `f'{x:{w}.2f}'`)
  - f-strings more concise than `format()` inside `print()` — especially when embedding multiple variables

---

### C.4 Python Dates

- **Functions:** `date()`
- **Methods:** `.isoformat()`, `.strftime()`
- **Concepts:**
  - `datetime` module must be imported — `from datetime import date` required before using the `date` type
  - `isoformat()` for simplest date string — returns `'yyyy-mm-dd'` format with no additional arguments
  - `strftime()` for full format control — uses `%` format codes (`%m`, `%d`, `%Y`, `%b`, `%-d`)
  - `%` format codes work in f-strings too — same codes usable inside f-string `{ }` braces for date objects
# APPENDIX D: Handling Errors with Exceptions
# Scope Map — p4da-ed2
# © Daniel Groner, Prospect Press.
# Derived from "Python for Data & Analytics, 2nd Ed." — For authorized educational use only.

---

### D.1 About Exceptions

- **Concepts:**
  - Runtime errors vs. syntax errors — a program with valid syntax can still encounter an error at runtime
  - Exception framework — Python generates errors in certain cases and allows programs to handle them rather than stopping immediately
  - Traceback — without exception handling, a runtime error produces a Traceback message and terminates the program
- **Traps:**
  - `ValueError` — `float()` called on a non-numeric string input; program terminates with Traceback if unhandled

---

### D.2 try/except

- **Keywords:** `try`, `except`
- **Concepts:**
  - `except` block as backup plan — runs only when an exception is raised in the `try` block; skipped entirely if no exception occurs
  - Graceful error handling — `try`/`except` allows the program to continue rather than crashing

---

### D.3 Exception Types and Multiple Error Handling

- **Keywords:** `except`
- **Concepts:**
  - Typed `except` for distinguishing errors — specifying exception types allows different responses to different errors
  - `except Exception as err` as catch-all — catches any exception type not already handled; `err` variable holds additional error details

---

### D.4 finally

- **Keywords:** `finally`
- **Concepts:**
  - `finally` for cleanup logic — runs whether or not an exception occurred; common uses include closing a file or database connection
  - `finally` always executes — after `try` if no error, or after `except` if error was caught

---

### D.5 Exceptions and Functions

- **Keywords:** `raise`
- **Functions:** `isinstance()`
- **Concepts:**
  - Two function outcomes — normal completion via `return`; error signaled via `raise`
  - Exception propagation — exception raised inside a function propagates up the calling chain until caught by `try`/`except` or program terminates
  - `raise` for meaningful error signals — lets programmer signal specific error conditions to callers rather than relying on Python's built-in messages
# APPENDIX E: Defining Classes: Object-Oriented Programming
# Scope Map — p4da-ed2
# © Daniel Groner, Prospect Press.
# Derived from "Python for Data & Analytics, 2nd Ed." — For authorized educational use only.

---

### E.1 About Object-Oriented Programming

- **Functions:** `type()`
- **Concepts:**
  - Three sources of types — built-in types, third-party package types (e.g., `DataFrame`), and user-defined types via `class`
  - Type as properties plus methods — a type is fundamentally a set of data (properties) and actions (methods) that can be performed on that data
  - Class is a synonym for type — `type(s)` returns `<class 'str'>` for a string variable

---

### E.2 An Example with Properties and Methods: Mortgage

- **Keywords:** `class`, `def`
- **Concepts:**
  - Class vs. object — class defines properties and methods available; object is a specific instance with specific values
  - `__init__()` retains properties — stores property values so subsequent methods can access them via `self.` without re-passing as arguments; why methods are more concise than equivalent functions
  - Methods vs. functions — method defined and indented within a class; called with variable prefix (e.g., `mortgage1.monthlyPayment()`); function called without prefix
  - Prefix jump mechanic — variable prefix to a method call is automatically passed as the `self` parameter
- **Traps:**
  - Defining without calling — a `def` block never called produces no output and no error

---

### E.3 Adding __str__() and __repr__() Methods

- **Concepts:**
  - `__str__()` for human-readable output — called by `print()` when printing a single object
  - `__repr__()` for computer-readable output — called when printing objects inside a list
  - `__repr__ = __str__` shorthand — class-level assignment makes both methods use the same logic
- **Traps:**
  - Printing without `__str__()` or `__repr__()` — produces memory-address string (e.g., `<__main__.Mortgage at 0x10566a828>`); not meaningful object data

---

### E.4 Adding a Class Variable: Rounding

- **Concepts:**
  - Class variable — defined inside `class` block but outside any method; shared across all instances
  - `ClassName.variableName` access pattern — used both to read and set a class variable
  - Changing a class variable affects all instances — `Mortgage.decimals = 0` affects all subsequent method calls on any `Mortgage` instance

---

### E.5 Adding a Method That Calls Another Method

- **Concepts:**
  - `self.methodName()` for intra-class calls — a method can call other methods of the same class; promotes reuse and avoids duplicating logic
  - Methods can reference class variables — e.g., `Mortgage.decimals` accessible inside any instance method

---

### E.6 Adding a Static Method: validate()

- **Keywords:** `@staticmethod`
- **Functions:** `isinstance()`
- **Concepts:**
  - Static method has no `self` — behaves like a function but defined within the class because the logic belongs conceptually to it
  - `@staticmethod` decorator — signals the method does not operate on a specific instance; decorators in general are beyond the scope of the book
  - Static method for pre-creation validation — validate parameters before constructing a class instance
- **Traps:**
  - `ValueError('Invalid amount')` — `validate()` raises if amount is not numeric or is `<= 0`
  - `ValueError('Invalid rate')` — raised if rate is not a `float` or is `<= 0`
  - `ValueError('Invalid term')` — raised if term is not an `int` or is `<= 0`

---

### E.7 The Complete Mortgage Class

- **Patterns:**
  - Validate then construct — call `ClassName.validate()` inside a `try` block before creating the instance; catch `ValueError` in `except` block
  - Full class integration — class variable, `__init__()`, `__str__()`/`__repr__()`, instance methods, static method, and `try`/`except` combined in one program
