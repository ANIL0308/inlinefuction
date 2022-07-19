/*If make a function as inline, then the compiler replaces the function calling location with the definition of the inline function at compile time.

Any changes made to an inline function will require the inline function to be recompiled again because the compiler would need to replace all the code with a new code; otherwise, it will execute the old functionality.

Syntax for an inline function:

inline return_type function_name(parameters)  
{  
   // function code?  
}   
Let's understand the difference between the normal function and the inline function.



Inside the main() method, when the function fun1() is called, the control is transferred to the definition of the called function. The addresses from where the function is called and the definition of the function are different. This control transfer takes a lot of time and increases the overhead.

When the inline function is encountered, then the definition of the function is copied to it. In this case, there is no control transfer which saves a lot of time and also decreases the overhead.

Let's understand through an example.

#include <iostream>  
using namespace std;  
inline int add(int a, int b)  
{  
    return(a+b);  
}  
int main()  
{  
    cout<<"Addition of 'a' and 'b' is:"<<add(2,3);A  
    return 0;  
  
}  
Once the compilation is done, the code would be like as shown as below:

#include<iostream>  
using namespace std;  
inline int add(int a, int b)  
{  
     return(a+b);   
}  
int main()  
{  
      cout<<"Addition of 'a' and 'b' is:"<<return(2+3);  
    return 0;  
}   
Why do we need an inline function in C++?

The main use of the inline function in C++ is to save memory space. Whenever the function is called, then it takes a lot of time to execute the tasks, such as moving to the calling function. If the length of the function is small, then the substantial amount of execution time is spent in such overheads, and sometimes time taken required for moving to the calling function will be greater than the time taken required to execute that function.

The solution to this problem is to use macro definitions known as macros. The preprocessor macros are widely used in C, but the major drawback with the macros is that these are not normal functions which means the error checking process will not be done during the compilation.

C++ has provided one solution to this problem. In the case of function calling, the time for calling such small functions is huge, so to overcome such a problem, a new concept was introduced known as an inline function. When the function is encountered inside the main() method, it is expanded with its definition thus saving time.

We cannot provide the inlining to the functions in the following circumstances:

If a function is recursive.
If a function contains a loop like for, while, do-while loop.
If a function contains static variables.
If a function contains a switch or go to statement
When do we require an inline function?

An inline function can be used in the following scenarios:

An inline function can be used when the performance is required.
It can be used over the macros.
We can use the inline function outside the class so that we can hide the internal implementation of the function.
Advantages of inline function
In the inline function, we do not need to call a function, so it does not cause any overhead.
It also saves the overhead of the return statement from a function.
It does not require any stack on which we can push or pop the variables as it does not perform any function calling.
An inline function is mainly beneficial for the embedded systems as it yields less code than a normal function.
Disadvantages of inline function
The following are the disadvantages of an inline function:

The variables that are created inside the inline function will consume additional registers. If the variables increase, then the use of registers also increases, which may increase the overhead on register variable resource utilization. It means that when the function call is replaced with an inline function body, then the number of variables also increases, leading to an increase in the number of registers. This causes an overhead on resource utilization.
If we use many inline functions, then the binary executable file also becomes large.
The use of so many inline functions can reduce the instruction cache hit rate, reducing the speed of instruction fetch from the cache memory to that of the primary memory.
It also increases the compile-time overhead because whenever the changes are made inside the inline function, then the code needs to be recompiled again to reflect the changes; otherwise, it will execute the old functionality.
Sometimes inline functions are not useful for many embedded systems because, in some cases, the size of the embedded is considered more important than the speed.
It can also cause thrashing due to the increase in the size of the binary executable file. If the thrashing occurs in the memory, then it leads to the degradation in the performance of the computer.*/
