
# debug_log.md
# Author: Ananda Ravinder

## Bug 1

Error type: KeyError

File + line: week8_buggy.py, line 14

What the error means: Python tried to access the dictionary key 'amount', but the first record used 'amout' instead. Since the key did not exist, Python raised a KeyError.

What I told the duck: The get_total function starts with a total of 0, loops through each record, adds the record's amount to the running total, and returns the final total. The error happens because the first record does not contain the expected key.

What I tried: I ran the original script and read the traceback from the bottom up. I added a DEBUG print inside the loop to inspect each record. The output showed that the first record used 'amout' instead of 'amount'.

How I fixed it: I corrected 'amout' to 'amount' in the first record, removed the DEBUG print, and ran the script again. This resolved the KeyError.

## Bug 2

Error type: TypeError

File + line: week8_buggy.py, line 19

What the error means: The is_over_limit function tried to compare an integer with the string '1000'. Python cannot compare these different data types using the greater-than operator.

How I fixed it: I removed the quotation marks around '1000', changing it to an integer. This allows the function to compare two numbers and correctly determine whether the amount exceeds the limit.

## After Fixing Both Bugs

Final output:

    Total: $5150.00 across 3 records
    True

Did pytest pass? Yes. All 13 tests passed, including the eight Week 7 tests and five Week 8 tests. Ruff formatting and linting checks also passed.

## AI Literacy Reflection

Did I use AI? Yes

If yes -- exact prompt I used:

"I ran the provided Week 8 Python script and used the traceback and DEBUG output to investigate the errors. The first error is a KeyError because the first record uses 'amout' while get_total() accesses 'amount'. After correcting that typo, the next error is a TypeError in the comparison amount > '1000'. Explain why each error occurs, how to correct it, and how the tests verify the fixes. Help me understand the reasoning rather than rewriting the entire program."

What AI explained: AI explained why a misspelled dictionary key causes a KeyError and why comparing an integer with a string causes a TypeError. It also explained how the pytest tests verify the total calculation, the approval limit, boundary conditions, and summary formatting. AI also assisted with the lab's code and instructions.

What I changed myself: I entered and saved the files, ran the original script, inspected the tracebacks and DEBUG output, applied the corrections, and ran Ruff and pytest to verify the results.

Can I explain every fixed line? Yes. The first correction makes the dictionary key match what the function expects. The second correction changes the threshold from a string to an integer so the comparison works correctly.

## What I learned

I learned how to read Python tracebacks from the bottom up and use DEBUG prints to inspect data when something goes wrong. I also learned how dictionary key errors and incompatible data types cause runtime errors, and how pytest can verify that the fixes work correctly.
