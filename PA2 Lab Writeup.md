# CSE 8A PA2 Lab

January 20, 2026

# Introduction

Welcome to your PA2 lab!

Today you will learn about **functions** in Python by building a weather temperature analyzer. You'll write functions that calculate average temperatures and categorize them as cold, warm, or hot.

A local weather station needs a program to help analyze daily temperature data. They record temperatures three times a day (morning, noon, and night) and want to automatically calculate the average temperature and determine if it's a cold, warm, or hot day. Your job is to write Python functions to help them!

## Learning Goals

By the end of this lab, you will be able to:

* Define functions with the `def` keyword
* Write functions that take parameters (inputs)
* Use the `return` statement to send results back
* Call functions and use their return values
* Perform calculations inside functions
* Use conditional logic (if/elif/else) in functions
* Return different types of values (numbers, strings, booleans)
* Test functions with different inputs

## Part 1: Understanding Functions

Before we start writing our weather analyzer, let's understand what functions are.

### What is a Function?

A **function** is a reusable block of code that performs a specific task. Think of it like a recipe:
* It has a **name** (like "make_pancakes")
* It can take **inputs** called **parameters** (like flour, eggs, milk)
* It does some **work** (mixing, cooking)
* It can give you back a **result** using `return` (delicious pancakes!)

### Function Syntax in Python

Here's the basic structure of a function:

```python
def function_name(parameter1, parameter2):
    # Do some work here
    result = parameter1 + parameter2
    return result
```

Let's break this down:
* `def` - keyword that tells Python "I'm defining a function"
* `function_name` - the name you give your function
* `(parameter1, parameter2)` - the inputs the function needs (can be zero, one, or many)
* The indented code - the work the function does
* `return result` - sends the result back to whoever called the function

### Example: A Simple Function

Here's a complete example:

```python
def add_two_numbers(num1, num2):
    total = num1 + num2
    return total
```

To **call** (use) this function:

```python
answer = add_two_numbers(5, 3)
print(answer)  # This will print 8
```

## Part 2: Calculate Average Temperature

Now let's write your first function for the weather station! 

### Task

The weather station records three temperatures each day:
* Morning temperature
* Noon temperature  
* Night temperature

Write a function called `average_temp` that takes three temperature values and returns the average.

**Step 1: Define Your Function**

Start by writing the function definition. Think about:
* What should you name the function? (We suggested `average_temp`)
* How many parameters do you need? (Hint: three temperature readings)
* What should you name the parameters? (Choose descriptive names like `morning`, `noon`, `night`)

Write the function header (the `def` line) in your `pa2_lab.py` file.

**Step 2: Calculate the Average**

Inside your function (remember to indent!), calculate the average of the three temperatures.

*Hint*: To find the average of three numbers, you add them all up and divide by 3.

Store the result in a variable. You might call it `avg` or `average`.

**Step 3: Return the Result**

Add a `return` statement to send the average back to whoever calls your function.

**Step 4: Test Your Function**

Below your function definition, write code to test your function:
* Call `average_temp` with three numbers (try 60, 75, and 65)
* Store the result in a variable
* Print the result with a descriptive label

Try calling it again with different numbers (like 50, 60, and 55). Run your program and check if the averages look correct!

**Expected Results:**
* Test 1: Should print `66.66666666666667` (or something close)
* Test 2: Should print `55.0`

**Debugging Tips:**
* If you get an error like "NameError: name 'average_temp' is not defined", make sure you defined the function BEFORE you try to call it
* If the average seems wrong, double-check your math formula
* Make sure your function has a `return` statement!

## Part 3: Categorize Temperature

Great job! Now the weather station wants to automatically categorize each day's temperature as "Cold", "Warm", or "Hot" based on the average temperature.

### Task

Write a function called `categorize_temp` that takes one parameter (the temperature) and returns a string describing the temperature category.

Use these rules:
* If the temperature is **less than 60**, return the string `"Cold"`
* If the temperature is **60 or higher but less than 80**, return the string `"Warm"`  
* If the temperature is **80 or higher**, return the string `"Hot"`

### Guided Steps

**Step 1: Write the Function Definition**

In your `pa2_lab.py` file (below your `average_temp` function), write the function header for `categorize_temp`.

Think about:
* How many parameters does this function need? (Hint: just one - the temperature to categorize)
* What should you call the parameter? (Something like `temp` or `temperature`)

**Step 2: Add the Conditional Logic**

Now you need to use `if`, `elif`, and `else` statements to check which category the temperature falls into.

Think about:
* Which condition should you check first? (Hint: start with the smallest range)
* What comparison operators do you need? (`<`, `>=`, etc.)
* What strings should you return? (Check the rules above - spelling and capitalization matter!)
* Remember: each condition should `return` the appropriate category string

*Structure hint*: You'll have one `if`, one `elif`, and one `else`. Each branch should return a different category string.

**Step 3: Test Your Function**

Below your function, write test cases to make sure it works correctly. Test these scenarios:
* A cold temperature (try 45 - should print "Cold")
* A warm temperature (try 70 - should print "Warm")
* A hot temperature (try 85 - should print "Hot")
* Boundary cases are important! Try:
  - 60 (should be "Warm" since 60 is the start of warm)
  - 80 (should be "Hot" since 80 is the start of hot)
  - 59 (should be "Cold" since it's just below 60)
  - 79 (should be "Warm" since it's just below 80)

Run your code and make sure all tests print the expected results!

**Common Mistakes to Avoid:**
* Using `=` instead of `==` for comparison (remember: `=` assigns, `==` compares)
* Forgetting quotes around strings like `"Cold"`, `"Warm"`, `"Hot"`
* Wrong order in if/elif/else (try to think: which condition should be checked first?)
* Forgetting to `return` the string

## Part 4: Putting It All Together

Excellent! Now let's combine both functions to create a complete weather analysis program.

### Task

Create a complete program that:
1. Asks the user for morning, noon, and night temperatures
2. Calculates the average temperature using your `average_temp` function
3. Categorizes the average using your `categorize_temp` function
4. Prints a nice summary

### Guided Steps

**Step 1: Get User Input**

At the bottom of your `pa2_lab.py` file (below all your test code, or you can delete the test code), add code to ask the user for three temperatures.

*Think about:*
* How do you ask the user for input in Python?
* What data type should you convert the input to? (Remember: temperatures can have decimals!)
* You'll need to do this three times - once for morning, once for noon, once for night
* Store each temperature in a separate variable with a descriptive name
* Use clear prompts like "Enter morning temperature: ", "Enter noon temperature: ", and "Enter night temperature: "

**Step 2: Calculate and Categorize**

Now use the two functions you wrote earlier to process the temperatures:
* Call your `average_temp` function with the three temperature variables you got from the user
* Store the result in a variable (maybe call it `average`)
* Then call your `categorize_temp` function with the average you just calculated
* Store that result in another variable (maybe call it `category`)

*Remember*: When you call a function, you need to pass the right number of arguments in the right order!

**Step 3: Print the Results**

Print two lines:
1. The average temperature with the label "Average temperature: " (round to 2 decimal places)
2. The category with the label "Category: "

*Think about*: 
* You have the average and category stored in variables from Step 2. How can you print them with labels?
* Use the `round()` function to round the average to 2 decimal places. Format: `round(number, 2)`

**Step 4: Test Your Complete Program**

Run your program and try different inputs:

**Test Case 1:**
* Morning: 55
* Noon: 68
* Night: 62

Expected output:
```
Enter morning temperature: 55
Enter noon temperature: 68
Enter night temperature: 62
Average temperature: 61.67
Category: Warm
```

**Test Case 2:**
* Morning: 85
* Noon: 92
* Night: 88

Expected output:
```
Enter morning temperature: 85
Enter noon temperature: 92
Enter night temperature: 88
Average temperature: 88.33
Category: Hot
```

**Test Case 3:**
* Morning: 45
* Noon: 52
* Night: 48

Expected output:
```
Enter morning temperature: 45
Enter noon temperature: 52
Enter night temperature: 48
Average temperature: 48.33
Category: Cold
```

### Reflection Questions

Take a moment to think about (you don't need to write these down):
* Why is it helpful to use functions instead of writing all the code in one place?
* What would you need to change if the weather station wanted different temperature categories?
* How would you modify the program to handle four temperature readings instead of three?

## Part 5: Lab Quiz (~15 mins)

Make sure to review the lab activity today! The lab quiz will test material based on what you learned in this lab.

## Challenge Problem: Handling Invalid Temperatures

**Note:** This challenge problem will NOT be on the lab quiz, but completing it will be very helpful for PA2! The PA requires you to handle error cases and return `None`, so this is great practice.

If you've completed all the lab activities and still have time, try this challenge!

### Task

The weather station has a problem: sometimes sensors malfunction and report impossible temperatures (like -200°F or 500°F). Let's make our program more robust!

Modify your `average_temp` function to check if any of the input temperatures are unrealistic. If any temperature is below -100 or above 150 degrees Fahrenheit, the function should return `None` instead of calculating the average.

### Guided Steps

**Step 1: Add Validation to `average_temp`**

Think about how to check if the temperatures are valid:
* What comparison operators do you need?
* How do you check if a temperature is "out of range"?
* Should you check all three parameters?

*Hint*: If ANY of the three temperatures are invalid, you should return `None`. Think about using `or` to combine conditions.

At the top of your `average_temp` function (before calculating the average), add an `if` statement that checks for invalid temperatures and returns `None` if found.

**Step 2: Update Your Main Program**

Now your `average_temp` function might return `None` instead of a number. You need to handle this case!

After you call `average_temp`, check if the result is `None`:
* If it is `None`, print: `"Error: Invalid temperature detected!"`
* If it's NOT `None`, continue with categorizing and printing the average temperature and category as normal

*Hint*: You can use `if average == None:` or `if average is None:` to check this.

**Step 3: Test with Invalid Inputs**

Run your program and try these test cases:

**Test with invalid morning temperature:**
```
Enter morning temperature: -150
Enter noon temperature: 70
Enter night temperature: 65
Error: Invalid temperature detected!
```

**Test with invalid noon temperature:**
```
Enter morning temperature: 75
Enter noon temperature: 200
Enter night temperature: 72
Error: Invalid temperature detected!
```

**Test with valid temperatures:**
```
Enter morning temperature: 55
Enter noon temperature: 68
Enter night temperature: 62
Average temperature: 61.67
Category: Warm
```


