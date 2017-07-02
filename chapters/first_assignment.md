# First Assignment: cleaning input

Your first assignment is to write a short python script to take a user's name, age, country of residence and favorite color and then print it out. There are some restrictions on the input that you can receive, however.  Here are the stipulations:

+ The following characters are not allowed: `/\+-;:{}()[]` and you should omit these characters if the code contains them.
+ If a user-supplied value exceeds 20 characters, you should preserve only 20 characters and append ' (truncated)' to the end.
+ Use the `raw_input` function to take user input, making sure that the values received are converted to the appropriate data type if necessary.
+ All input but name are optional 

You should print the attribute and the value back out at the end like this:

````
Name: Mork
Age: 42
Country of Residence: Unites States
Favorite color: blue
````

Make sure to test your code with examples that violate the restrictions to make sure it is correct.
