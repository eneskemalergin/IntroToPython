Designing New Functions: A Recipe
---

Writing a good essay requires planning: deciding on a topic, learning the background material, writing an outline, and then filling in the outline until you’re done.

Writing a good function also requires planning. You have an idea of what you want the function to do, but you need to decide on the details: What do you name the function? What are the parameters? What does it return?

This section describes a step-by-step recipe for designing and writing a function. Part of the outcome will be a working function, but almost as important is the documentation for the function. Python uses three double quotes to start and end this documentation; everything in between is meant
for humans to read. This notation is called a ```docstring```, which is short for documentation string.

Here is an example of a completed function. We’ll show you how we came up with this using a function design recipe (FDR), but it helps to see a completed example first:

```Python
def days_difference(day1, day2):
	""" (int, int) -> int

	Return the number of days between day1 and day2, which are
	both in the range 1-365 (thus indicating the day of the
	year).

	>>> days_difference(200, 224)
	24
	>>> days_difference(50, 50)
	0
	>>> days_difference(100, 99)
	-1
	"""
	return day2 - day1
```

Here are the parts of the function, including the docstring:

- The first line is the function header.
- The second line has three double quotes to start the docstring. The (int, int) part describes the types of values expected to be passed to parameters day1 and day2, and the int after the -> is the type of value the function will return.
- After that is a description of what the function will do when it is called. It mentions both parameters and describes what the function returns.
- Next are some example calls and return values as we would expect to see in the Python shell. (We chose the first example because that made day1 smaller than day2, the second example because the two days are equal, and the third example because that made day1 bigger than day2.)
- The last line is the body of the function.

---

There are six steps to the function design recipe. It may seem like a lot of work at first, but this recipe can save you hours of time when you’re working on more complicated functions.

1. _Examples._ The first step is to figure out what arguments you want to give to your function and what information it will return. Pick a name (often a verb or verb phrase): this name is often a short answer to the question, “What does your function do?” Type a couple of example calls and return values. 

We start with the examples because they’re the easiest: before we write anything, we need to decide what information we have (the argument values) and what information we want the function to produce (the return value). Here are the examples from ```days_difference```:

```Python
	>>> days_difference(200, 224)
	24
	>>> days_difference(50, 50)
	0
	>>> days_difference(100, 99)
	-1
```

2. _Type Contract._ The second step is to figure out the types of information your function will handle: Are you giving it integers? Floating-point numbers? Maybe both? We’ll see a lot of other types in the upcoming chapters, so practicing this step now while you only have a few choices will help you later. If the answer is, “Both integers and floating-point numbers,” then use the word number.

Also, what type of value is returned? An integer, a floating-point number, or possibly either one of them?

This is called a _contract_ because we are claiming that if you call this function with the right types of values, we’ll give you back the right type of value. (We’re not saying anything about what will happen if we get the wrong kind of values.) Here is the type contract from ```days_difference```:

```Python
	""" (int, int) -> int
```

3. _Header._ Write the function header. Pick meaningful parameter names to make it easy for other programmers to understand what information to give to your function. Here is the header from ```days_difference```:

```Python
def days_difference(day1, day2):
```

4. _Description._ Write a short paragraph describing your function: this is what other programmers will read in order to understand what your function does, so it’s important to practice this! Mention every parameter in your description and describe the return value. Here is the description from ```days_difference```:

```Python
	'''Return the number of days between day1 and day2, which areboth in the range 1-365 (thus indicating the day of the year).
	'''
```

5. _Body._ By now, you should have a good idea of what you need to do in order to get your function to behave properly. It’s time to write some code! Here is the body from ```days_difference```:

```Python 
	return day2 - day1
```

6. _Test._ Run the examples to make sure your function body is correct. Feel free to add more example calls if you happen to think of them. For days_difference, we copy and paste our examples into the shell and compare the results to what we expected:
