# coding_noob
Helpful information for coding noobs

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
