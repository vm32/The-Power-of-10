# The Power of 10 — NASA’s Rules for Coding

1. **Restrict All Code to Very Simple Control Flow Constructs**
   - Avoid complex constructs such as `goto` and recursion.
   - **Example**:
     ```c
     // Avoid
     void example() {
         goto error;
     error:
         // handle error
     }

     // Prefer
     void example() {
         if (condition) {
             // handle error
         }
     }
     ```

2. **Give All Loops a Fixed Upper-Bound**
   - Ensure loops have a predetermined maximum number of iterations.
   - **Example**:
     ```c
     // Avoid
     while (condition) {
         // loop body
     }

     // Prefer
     for (int i = 0; i < MAX_ITERATIONS; i++) {
         if (!condition) break;
         // loop body
     }
     ```

3. **Do Not Use Dynamic Memory Allocation After Initialization**
   - Avoid `malloc`, `new`, or similar constructs after program initialization.
   - **Example**:
     ```c
     // Avoid
     void process() {
         char* buffer = (char*)malloc(SIZE);
         // use buffer
         free(buffer);
     }

     // Prefer
     void init() {
         static char buffer[SIZE];
         // initialize buffer
     }

     void process() {
         extern char buffer[SIZE];
         // use buffer
     }
     ```

4. **No Function Should Be Longer Than What Can Be Printed on a Single Page**
   - Keep functions short and concise, typically less than 60 lines.
   - **Example**:
     ```c
     // Avoid
     void longFunction() {
         // 100+ lines of code
     }

     // Prefer
     void shortFunction1() {
         // 30 lines of code
     }

     void shortFunction2() {
         // 30 lines of code
     }
     ```

5. **Use Assertion to Verify Critical Assumptions**
   - Employ assertions to check for conditions that should never happen.
   - **Example**:
     ```c
     // Avoid
     void example(int value) {
         if (value < 0) {
             // handle error
         }
     }

     // Prefer
     void example(int value) {
         assert(value >= 0);
         // continue processing
     }
     ```

6. **Declare Data Objects at the Smallest Possible Scope**
   - Limit the scope of data objects to reduce complexity.
   - **Example**:
     ```c
     // Avoid
     int globalVariable;

     void example() {
         globalVariable = 10;
         // use globalVariable
     }

     // Prefer
     void example() {
         int localVariable = 10;
         // use localVariable
     }
     ```

7. **Check the Return Value of All Non-Void Functions**
   - Always handle or verify return values from functions.
   - **Example**:
     ```c
     // Avoid
     void example() {
         openFile("file.txt");
     }

     // Prefer
     void example() {
         if (openFile("file.txt") == -1) {
             // handle error
         }
     }
     ```

8. **Limit the Number of Function Parameters to a Minimum**
   - Aim for functions with no more than seven parameters.
   - **Example**:
     ```c
     // Avoid
     void example(int a, int b, int c, int d, int e, int f, int g, int h) {
         // function body
     }

     // Prefer
     void example(int a, int b, int c, int d) {
         struct params {
             int e, f, g, h;
         } p;
         // function body
     }
     ```

9. **Use the Preprocessor Sparingly**
   - Minimize the use of macros; prefer inline functions and constants.
   - **Example**:
     ```c
     // Avoid
     #define MAX_SIZE 100

     // Prefer
     const int MAX_SIZE = 100;
     ```

10. **Use Simple, Clear Naming Conventions**
    - Ensure all names are descriptive and consistent across the codebase.
    - **Example**:
     ```c
     // Avoid
     int a;

     // Prefer
     int counter;
     ```

By adhering to these rules, developers can create more reliable, maintainable, and understandable code, especially in environments where safety and correctness are paramount.
