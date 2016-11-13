# Our First Program

Before we get into the atomic parts of Python, let's dive right in and write a script so we know what it *feels* like to write some code. Type the following out manually and then run it:

    first_name = 'Vera' 
    age = 42 
    favorite_things = ['Greek Yogurt', 'Soft Rock', 'Philosophy']

    print('first name: ', first_name)
    print('age: ', age)
    print('Here are some of my favorite things: ')

    for thing in favorite_things:
        print(thing)

To run this script without errors, you need to copy it exactly as it is. A common 'gotcha' for those new to Python is indentation. Indentation is necessary and incorrect indentation will cause errors. When you see indentation, my advice is to always type 4 spaces (and not a tab).  Do your best to power through until you see the correct output, which should look similar to this:

    first_name: Vera
    age: 42
    Here are some of my favorite things: 
    Greek Yogurt
    Soft Rock
    Philosophy

## Reflect! 

Congratulations, you just wrote your first Python program! This isn't easy, so take a minute and reflect on your success. What do you think you did here? Try to formulate any questions you might have.

## Our First Error: The NameError

Now that we've done something right, let's do something wrong. I am going to take an 'error-first' approach in this guide, as it more closely aligns with what writing code is like in the real world.  Learning how to make sense of error messages is a very efficient way to learn a programming lanaguage.

Let's add two lines in between `first_name` and `age`:

    city = Chicago
    state = Illinois

So what you should have is this:

    first_name = 'Vera'
    city = Chicago
    state = Illinois
    age = 42

    print(first_name)
    print(city)
    print(state)
    print(age)

Run this code. You should see output like this:

    Traceback (most recent call last):
      File "first_program.py", line 2, in <module>
        city = Chicago
    NameError: name 'Chicago' is not defined

and then ask yourself the following questions:

+ What is the error called?
+ Which line is it on?
+ Do you have an idea of how to fix it?

## Errors Tell You Where to Look and What to Look for 

The name of the error is ... well ...  **'NameError'**.  We should look into what that is. I went ahead and Googled 'Python3 NameError' and have extracted the relevant bit for us:

> Raised when a local or global name is not found. 

Okay, so *something* that Python calls a 'name' was not found. What was not found? Let's look at the line the error is telling us about, line 2. 

Okay, here it is:

    city = Chicago

And looking back at our error message, we see some further information about the error, namely that it concerns the use of 'Chicago': 

    Traceback (most recent call last):
      File "first_program.py", line 2, in <module>
        city = Chicago
    NameError: name 'Chicago' is not defined <-- RIGHT HERE

At this point, we are fairly certain that we're looking at the right line. Maybe you even realize by comparison how to fix the error. If we look above city to the place where it says:

    first_name = 'Vera'

we'll notice that the thing to the right of the equals has quotes around it. But `Chicago` doesn't have quotes. Let's fix that.

    first_name = 'Vera'
    city = 'Chicago'

Run the code again.  What do you see? Another **NameError**! Fortunately, we have pretty much the same error message, but on line 3: 

    Traceback (most recent call last):
      File "first_program.py", line 3, in <module>
        state = Illinois
    NameError: name 'Illinois' is not defined

This time the error concerns our use of 'Illinois'. So let's fix line 3:

    first_name = 'Vera'
    city = 'Chicago'
    state = 'Illinois'

If we run our program again, we should see the output we hoped to get. 

# What is a Name?

Success! We fixed the program.  But we did so largely through thinking by analogy: we saw a similarity between another line of code that didn't have a bug and fixed the problematic line by reproducing the working structure. But this didn't get us to the point of understanding of why the **NameError** really occurred and how to avoid running into it in the future.

Let's think about what we know now. When `Chicago` had no quotes around it, Python told us two things:

- `Chicago` is a name
- the name `Chicago` can't be found anywhere (locally or globally) 

But, when we put quotes around it, the **NameError** disappeared. I'm going to nudge us forward a little by asserting this:

> When `Chicago` is surrounded in quotes, it is no longer a name. It's now a value.

Let's think of a name for now as **a connection to a value**. The name `first_name` connects to the value `'Vera'`. And for a moment, let's think of a program in a very limited sense as a collection of names connected to values. We give values names in order to refer to them later and do interesting things with them. And the referral process is conceptually like looking up someone's phone number in a telephone book. If you look up a person's name and it's in the phone book, you get his or her phone number. Think of a Python program as a thing that runs in a larger Python environment that uses a storage mechanism conceptually like this phone book.  When we, the programmer, write:

    first_name = 'Vera'

we are saying to the Python environment: "I want to store the value 'Vera' under the name 'first_name'". When I write code like:

    print(first_name)

We are asking the environment to go to its 'phone book' and retrieve the value listed under the name `first_name` and print that value.  

To recap what our error was: we said to the Python phonebook, "here is a name, city. please connect this name to a value that doesn't exist".  Python understandably threw its hands up and returned a **NameError**.


