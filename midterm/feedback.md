# Notes on the Midterm

* _Correctness    (out of 40):_ 39
* _Good Practices (out of 10):_  9
* _Docs / Testing (out of 10):_ 10

_Details on the grading criteria for the midterm can be found on [Canvas](https://canvas.slu.edu/courses/28045/rubrics/23671)._

Overall, nicely done.  There were a couple of minor errors in the code and a few note on good programming practices I've included below.

Thank you for your active participation in class. I appreciate the questions, interaction, and humor.


## Step 1
Good work.

## Step 2
Below is some general feedback on testing, but you didn't lose any points:
* Since you have two different code branchs (found and not found), it would be good to have a test condition that verifies the "if the code are not found, then return None" scenario.
* For fully complete unit tests, it would be good to create some situations where the billing code IS found, but not with that service code.
* Think about multiple tests and "edge conditions"

## Step 3
You lost 1 point under Good Practices based on the feedback below:
* While your first condition `date == 0 and int(pat_age) >= 65 == 0` does pass all of the tests, the extra `==0` at the end is incorrect.  The test condition should have just been `date == 0 and int(pat_age) >= 65`.  
* In fact, you have simplified the conditions if you chose to. It's a trade off. The way you wrote it literally follows the requirements I presented and would make traceability more clear.  Simplifying the conditions to simply `if int(pat_age) >= 65` would have been less code.  Either way is correct.
* I'm not a fan of you trying to explicitly cover all conditions.  Usually, we use the `else` for anything that doesn't fall into one of the _special_ rules.  You've tried to cover the default case when an explicit `elif date != 0 and int(pat_age) < 65`.  The logic is correct, but I think it's more confusing.  Your `else` condition should never be run, but if something strange happened that lead to it, you wouldn't know if there was a break in the logic or if the rate wasn't found.  `None` is supposed to mean the date wasn't found.

## Step 4
You lost 1 point under Correctness:
* Near the beginning of your function, you specify `CSV="/data/visits.csv"` meaning your code will only ever work for that one file.  It should have used the `visit` parameter instead.
