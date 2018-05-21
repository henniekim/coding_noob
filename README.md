# coding_noob
Helpful information for coding noobs
All code is executed in linux 14.0.3

# List 

* [Using g++ compiler](#Using-g++-compiler)  
* [Using g++ compiler to link sources](#Using-g++-compiler-to-link-sources)   
* [Make shell script](#Make-shell-script)  
* [Using 'Cmake'](#Using-\'Cmake\')  

# Using g++ compiler
Here is the basic c code example. 

1. Use any text editor (vim is recommended) to make "hello.cpp". Type as below and save as "hello.cpp"
```
#include <stdio.h>

int main()
{
  printf("hello world!\n");
  return 0;
}
```
2. Now we use g++ compiler to make 'object file' (\*.o)
```
$ g++ -o hello hello.cpp 
```
3. Execute file 
```
$ ./hello
```
4. You can see the result as below
```
hello world!
```

# Using g++ compiler to link sources
1. Use any text editor to make "main.cpp". Type as below and save as "main.cpp"
```
#include <stdio.h>
void myfunction();

int main()
{
  printf("hello world!\n");
  myfunction();
  return 0;
}
```
2. Type as below and save as "myfunction.cpp"
```
#include <stdio.h>
void myfunction()
{
  printf("my function!\n");
}
```
3. Compile together 
```
g++ -o hellofunc main.cpp myfunction.cpp
```

4. You can see the result as below
```
hello world!
my function
```
# Using g++ compiler to link sources (compile first link after)
1. Use any text editor to make "main.cpp" Type as below and save as "main.cpp"
```
extern void myfunction();

int main()
{
  myfunction();
  myfunction();
  return 0;
}
```
2. Type as below and save as "myfunction.cpp"
```
#include <stdio.h>

void myfunction()
{
  prinf("hello world!\n");
}
```
3. Compile firakefile'
st 
```
$ g++ -c main.cpp
$ g++ -c myfunction.cpp
```
4. Link together 
```
$ g++ main.o myfunction.o -o link
```
5. Execute file
```
$ ./link
```
6. See the result as below
```
hello world!
hello world!
```

# Make shell script
1. Open any text editor and type as below. Save as "myscript.sh"
```
g++ -c main.cpp
g++ -c myfunction.cpp
g++ main.o myfunction.o -o link
```

2. Execute bash script file to compile and link files.
```
$ bash ./myscripts.sh
```

3. See the result as below
```
hello world!
hello world!
```

# Using 'Cmake'
1. Type as below and save as "CMakeLists.txt"
```
cmake_minimum_required(VERSION 3.6)
project(cmake_example)
set(CMAKE_CXX_STANDARD 14)
set(SOURCE_FILES main.cpp myfunction.cpp)
add_executable(cmake_example ${SOURCE_FILES})
```
2. Using 'cmake' to generate "Makefile" file. (It sounds wierd but the name of file is "Makefile".)
```
cmake CMakeLists.txt
```
3. Using 'make' command to compile.
```
make
```
4. You can see the result as below
```
[33%] Building CXX object CMakeFiles/cmake_example.dir/myfunction.cpp.o
[66%] Building CXX object CMakeFiles/cmake_example.dir/main.cpp.o
[100%] Linking CXX executable cmake_example
[100%] Build target cmake_example
```
5. Execute and check the result
```
./cmake_example
hello world!
hello world!
```
