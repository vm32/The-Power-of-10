# The Power of 10 — NASA’s Rules for Coding

1. **Restrict All Code to Very Simple Control Flow Constructs**
   - Avoid complex constructs such as `goto` and recursion.

2. **Give All Loops a Fixed Upper-Bound**
   - Ensure loops have a predetermined maximum number of iterations.

3. **Do Not Use Dynamic Memory Allocation After Initialization**
   - Avoid `malloc`, `new`, or similar constructs after program initialization.

4. **No Function Should Be Longer Than What Can Be Printed on a Single Page**
   - Keep functions short and concise, typically less than 60 lines.

5. **Use Assertion to Verify Critical Assumptions**
   - Employ assertions to check for conditions that should never happen.

6. **Declare Data Objects at the Smallest Possible Scope**
   - Limit the scope of data objects to reduce complexity.

7. **Check the Return Value of All Non-Void Functions**
   - Always handle or verify return values from functions.

8. **Limit the Number of Function Parameters to a Minimum**
   - Aim for functions with no more than seven parameters.

9. **Use the Preprocessor Sparingly**
   - Minimize the use of macros; prefer inline functions and constants.

10. **Use Simple, Clear Naming Conventions**
    - Ensure all names are descriptive and consistent across the codebase.

By adhering to these rules, developers can create more reliable, maintainable, and understandable code, especially in environments where safety and correctness are paramount.
