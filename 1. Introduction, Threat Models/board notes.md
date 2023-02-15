## what can go wrong in policies
![image](https://user-images.githubusercontent.com/72671239/218936215-c98c6844-a865-4c64-a991-70a7aa6173e2.png)

## what can go wrong in mechanisms
https://github.com/hackappcom/ibrute/blob/master/id_brute.py
http://blog.hackapp.com/2014/09/what-if-i-was-cloud.html
![image](https://user-images.githubusercontent.com/72671239/218938452-b03ff3a9-0030-4305-b856-cabefd40be49.png)

## C browser vs SSL =>  Null	byte	vs.	length-encoding
browser keep url in memory, reads it till it find end of string \0 terminiting zero, while the SSL certificates doesnt do that

discoverd by moxie marlinspike
![image](https://user-images.githubusercontent.com/72671239/218961694-bb0360c2-1955-4354-b700-d6ff8293a5cc.png)

## Buffer Overflow

https://stackoverflow.com/questions/45583473/include-errors-detected-in-vscode

[The term 'gcc' is not recognized as the name of a cmdlet, function SOLVED in Visual Studio Code
](https://www.youtube.com/watch?v=DDeFWwW_BYQ)

```c
#include <stdio.h>

int read_req(void) {
    char buf[128];
    int i;
    gets(buf);
    i = atoi(buf);
    return i;
}

int main(int ac, char **av)
{
    int x = read_req();
    printf("x=%d\n", x);
}
```
```powershell
more .\bufferoverflow.c
```
is a Windows command that displays the contents of the file "bufferoverflow.c" in the command prompt, one page at a time, It is commonly used to view the contents of large text files, such as program source code.

![image](https://user-images.githubusercontent.com/72671239/218980570-a55ea902-e28d-4807-b530-27a68057cba3.png)

compile the file using the follwoing 
```powershell
gcc -o compiledfile .\bufferoverflow.c -I.
```

![image](https://user-images.githubusercontent.com/72671239/218988477-c5076208-5ffe-4998-8816-ea38eb97e139.png)

when running the .exe file, the program return 0 to charecters and if the number is too large it return a number within the int range, but when very large input of charecters or numbers is provided, the program doesnt return anything 

![image](https://user-images.githubusercontent.com/72671239/219035890-a24ad336-b512-4602-b4a5-ea90bb471728.png)

run in debugger mode 
```powershell
gdb .\compiledfile.exe
```
in x86 architecture, the ESP (Extended Stack Pointer) register is used as the stack pointer. The ESP register points to the current top of the stack, and it is updated automatically by the CPU whenever data is
![image](https://user-images.githubusercontent.com/72671239/219037233-a940d9a9-d3ad-4c06-b3ad-72003dc565fb.png)
![image](https://user-images.githubusercontent.com/72671239/219042620-bfe2f213-5f1f-4e97-840d-8f3618349473.png)

the bufferoverflow here caused the values in the stack to be overwritten and all the inportant registers now have the value 0x41 which is the letter 'a', all memory addresses from &buf[0] till the end of the input length have the same value of input 'a'
![image](https://user-images.githubusercontent.com/72671239/219045803-8854cd71-7202-4d63-8ac7-d4b53ecc685a.png)







