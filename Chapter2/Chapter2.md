# 第二章笔记

## Q & A

1. **Q:** What's the meaning of the first sentence?

  ```c++
  int main()  // C++ programs start by executing the function main
  {
      cout << "Hello, World!\n";  // output “Hello, World!”
      return 0;
  }
  ```
  > First it’ll write Hello, World! to the screen, and then it will return a value 0 (zero) to whoever called it.
  > Since main() is called by “the system,” we won’t use that return value.
  > However, on some systems (notably Unix/Linux) it can be used to check whether the program succeeded.
  > A zero (0) returned by main() indicates that the program terminated successfully.

  **A:**  第一句`cout << "Hello, World!\n;"`会在屏幕上输出"Hello, World!"。第二句`return 0;`会返回零给调用`main`的函数。`main`是每个C++程序的入口（即每个C++程序开始执行的地方），同时每个C++程序都是由操作系统（比如Windows）来执行调用的（即当双击编译好后的exe文件），其调用的就是（exe文件中的）`main`这个函数。操作系统本身也是一个程序，在操作系统中执行另一个程序其实就是调用这个程序的`main`函数，而调用这个`main`函数的caller本身在操作系统中自然也是一个函数。在Windows中，貌似一般不关心`main`函数的返回值；而在Linux等系统中则会以零作为执行成功，非零表示执行失败。

## BASIC LOGIC LINE

```c++
#include <iostream>
int main()
{
	std::cout<<"Hello World!\n";
}
```

**P.S**: 
“\n” means going nextline

### Review

1. What is the purpose of the “Hello, World!” program?
  * To show the “Hello, world!” in the screen

2. Name the four parts of a function.
  * A return type, here `int`;
  * A name, here `main`; 
  * A parameter list enclosed in parentheses; 
  * A function body enclosed in a set of “curly braces,” `{ }` ;

3. Name a function that must appear in every C++ program.
  * `main()`

4. In the “Hello, World!” program, what is the purpose of the line `return 0;` ?
  * Since `main()` is called by “the system,” we won’t use that return value.

5. What is the purpose of the compiler?
  * Translate it from the human-readable form to something a machine can “understand.”

6. What is the purpose of the `#include` directive?
  * It instructs the computer to make available (“to include”) facilities

7. What does a `.h` suffix at the end of a file name signify in C++?
  * It is called a header or a header file.  A header contains definitions of terms that we use in our program.

8. What does the linker do for your program?
  * To link several separate parts together to form an executable program

9. What is the difference between a source file and an object file?
  * What you read and write is called source code or program text, and what the computer executes is called executable, object code, or machine code.

10. What is an IDE and what does it do for you?
  * IDE: interactive development environment;
  * To do the compile and link commands

11. If you understand everything in the textbook, why is it necessary to practice?
  * To assure our thinking.

### Terms

1. **`//`**: Anything written after the token `//` (that’s the character `/`, called “slash,” twice) on a line is a comment, which are ignored by the computer.

2. **`<<`**: output operator, `<<`

3. **C++**: C++ is a programming language designed for a wide selection of programming tasks

4. **Comment**: Comments are written to describe what the program is intended to do and in general to provide information useful for humans that can’t be directly expressed in code.  In addition, comments are a reminder of what the code does, in case that the programmer forget the purpose long after writing the code.

5. **Compiler**: To get a program to run, you must first translate it from the human-readable form to something a machine can “understand.”

6. **Compile-time error**: Errors found by the compiler

7. **`cout`**: The name `cout` refers to a standard output stream

8. **Executable**: The code that the computer executes is called executable

9. **Function**: A function is basically a named sequence of instructions for the computer to execute in the order in which they are written.

10. **Header**: A header contains definitions of terms, such as `cout`, that we use in our program

11. **IDE**: interactive development environment

12. **`#include`**: It instructs the computer to make available (“to include”) facilities from a header file, such as `std_lib_facilities.h`. We wrote that file to simplify use of the facilities available in all implementations of C++

13. **library**: the C++ standard library

14. **linker**: A program usually consists of several separate parts, often developed by different people. For example, the “Hello, World!” program consists of the part we wrote plus parts of the C++ standard library. These separate parts (sometimes called translation units) must be compiled and the resulting object code files must be linked together to form an executable program. The program that links such parts together is (unsurprisingly) called a linker

15. **`main()`**:Every C++ program must have a function called `main` to tell it where to start executing.

16. **Object code**: The code that computer executes is called executable, object code

17. **Output**: 

18. **Program**: A program usually consists of several separate parts

19. **Source code**: What you read and write is called source code or program text,

20. **Statement**: 

