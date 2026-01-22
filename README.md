# CSE 8A Winter 2026 PA2

**Due Date: Sunday, January 25, 2026, 11:59 PM PST**

## Provided Files
None

## File(s) to Submit
- `is_late.py`
- `grade_calculator.py`

(Details on how to submit your files can be found below)

## Part 1. Implementation (100 points)

In this programming assignment, you will implement two separate Python functions in two different files. Each function solves a different problem, and both will be tested independently on Gradescope.

### Overview of the Two Functions

1. **`is_late(minutes_late)`** - Determines if a student is considered late for a lab
2. **`calculate_final_grade(participation, discussion, midterm, labs, pa, final)`** - Calculates a student's final letter grade

## Part 2. Function 1: `is_late` (30 points)

### Part 2.1 Task Description

Your task is to write a function taking in a numeric parameter `minutes_late` and return the boolean value `True` or `False` to determine whether a student is considered late or not for a lab.

The condition is defined below:
- If the input is **negative** or **50 or more minutes late**, this is an error case → return `None`
- If the student arrives **5 or more minutes late** but **less than 50 minutes late**, they are considered late → return `True`
- If the student arrives **less than 5 minutes late**, they are not considered late → return `False`

### Part 2.2 Implementation Details

1. Create a new file called `is_late.py`. The file name must match exactly to pass the tests.

2. Define a function called `is_late` that takes one parameter:
   - `minutes_late`: a number (int or float) representing how many minutes late a student is for lab

3. Implement the logic:
   ```python
   def is_late(minutes_late):
       # First, check for error cases
       # Return None if minutes_late is negative OR >= 50
       
       # Then check if it's late (>= 5 and < 50)
       # Return True if late
       
       # Otherwise it's on time or slightly late (>= 0 and < 5)
       # Return False
   ```

### Part 2.3 Examples

Here are some examples of how your `is_late` function should behave:

```python
>>> is_late(0)
False

>>> is_late(-1)
None

>>> is_late(50)
None

>>> is_late(49.9)
True

>>> is_late(4.5)
False
```


## Part 3. Function 2: `calculate_final_grade` (70 points)

### Part 3.1 Task Description

You will write a function called `calculate_final_grade` that calculates a student's final letter grade based on their grades in different course categories. This function uses the actual grading scheme from our CSE 8A syllabus!

According to our syllabus, your final grade is determined by these percentages:
- **Class participation**: 5%
- **Discussion Quizzes**: 15%
- **Midterm**: 15%
- **Labs**: 16%
- **PA (Programming Assignments)**: 24%
- **Final exam**: 25%

The standard grading scale is:
- **A**: 90 or above
- **B**: 80 to 89.99999
- **C**: 70 to 79.99999
- **D**: 60 to 69.99999
- **F**: below 60

### Part 3.2 Implementation Details

1. Create a new file called `grade_calculator.py`. The file name must match exactly to pass the tests.

2. Define a function called `calculate_final_grade` that takes **six parameters** (all are grades out of 100):
   - `participation`: class participation grade
   - `discussion`: discussion quizzes grade
   - `midterm`: midterm exam grade
   - `labs`: labs grade
   - `pa`: programming assignments grade
   - `final`: final exam grade

3. Calculate the weighted average using the percentages above:
   ```python
   def calculate_final_grade(participation, discussion, midterm, labs, pa, final):
       # Calculate the weighted average
       # final_percentage = participation * 0.05 + discussion * 0.15 + ...
       
       # Determine the letter grade based on final_percentage
       # Return 'A', 'B', 'C', 'D', or 'F' as a string
   ```

4. **Important**: Your function must return the letter grade as a **string**: `'A'`, `'B'`, `'C'`, `'D'`, or `'F'`.

### Part 3.3 Examples

```python
# Perfect score in everything
calculate_final_grade(100, 100, 100, 100, 100, 100)  # Returns 'A'

# All categories at 90
calculate_final_grade(90, 90, 90, 90, 90, 90)  # Returns 'A'

# All categories at 85
calculate_final_grade(85, 85, 85, 85, 85, 85)  # Returns 'B'

# All categories at 75
calculate_final_grade(75, 75, 75, 75, 75, 75)  # Returns 'C'

# All categories at 65
calculate_final_grade(65, 65, 65, 65, 65, 65)  # Returns 'D'

# All categories at 50
calculate_final_grade(50, 50, 50, 50, 50, 50)  # Returns 'F'

# Mixed scores (more realistic):
# participation=95, discussion=88, midterm=92, labs=90, pa=85, final=87
# Calculation: 95*0.05 + 88*0.15 + 92*0.15 + 90*0.16 + 85*0.24 + 87*0.25
#            = 4.75 + 13.2 + 13.8 + 14.4 + 20.4 + 21.75
#            = 88.3
calculate_final_grade(95, 88, 92, 90, 85, 87)  # Returns 'B'
```

## Part 4. Submission

Once you are confident that your programs are correct, you may submit them to Gradescope. 

**You must submit BOTH files:**
1. `is_late.py`
2. `grade_calculator.py`

The file names have to match exactly to pass the autograder.

### How to Submit to Gradescope

1. Go to Gradescope and find the PA2 assignment
2. Upload both `is_late.py` and `grade_calculator.py`
3. Click "Submit"
4. Wait for the autograder to run

### Understanding Your Results

**For this PA, we have 20 test cases in total** (10 for each function):
- 9 visible tests for `is_late` (you can see what they test)
- 1 hidden test for `is_late`
- 9 visible tests for `calculate_final_grade` (you can see what they test)
- 1 hidden test for `calculate_final_grade`

If you got any test cases wrong, you may have feedback that shows:
- The test name (which tells you what it's testing)
- The input parameters that were used
- The expected output
- Your actual output

For example, if you see:
```
Test 5 minutes late (boundary)
Parameter: 5
Expected Output: True
Actual Output: False
```

This means when we called `is_late(5)`, we expected `True` but your function returned `False`.

Don't worry if you don't pass everything on the first try! You can submit multiple times. Use the feedback to debug your code and resubmit.

When you pass all public test cases, you should get at least 90/100 points. As a reminder, Gradescope won't displace score until grades are published.
