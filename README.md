# Usage of const keyword and & operator
## Usage of const
* Constant Variables
    * If you make any variable as constant, using const keyword, you cannot change its value. Also, the constant variables must be initialized while they are declared.
#### Example C++
  ```c++
int main
{
    const int i = 10;
    const int j = i + 10;     // works fine
    i++;    // this leads to Compile time error   
}
```
* Pointers with const keyword
    * can apply const to what the pointer is pointing to, or we can make the pointer itself a constant.
        * Pointer to a const variable
      ```c++
      const int* u;
      ```
      ```c++
      char const* v;
      ```
    * const Pointer
  ```c++
  int x = 1;
  int* const w = &x;
  ```
* const Function Arguments and Return types
#### Example C++
```c++
void f(const int i)
{
    i++;    // error
}

const int g()
{
    return 1;
}
```
* Defining Class Data members as const
#### Example C++
```c++
class Test
{
    const int i;
    public:
    Test(int x):i(x)
    {
        cout << "\ni value set: " << i;
    }
};

int main()
{
    Test t(10);
    Test s(20);
}
```
* Defining Class Object as const
#### Example C++
```c++
const class_name object;
```
```c++
const Test r(30);
```
* Defining Class's Member function as const
#### Example C++
```c++
return_type function_name() const;
```
```c++
class StarWars
{
    public:
    int i;
    StarWars(int x)    // constructor
    { 
        i = x; 
    }

    int falcon() const  // constant function
    { 
        /* 
            can do anything but will not
            modify any data members
        */
        cout << "Falcon has left the Base";
    }

    int gamma()
    { 
        i++; 
    }
};

int main()
{
    StarWars objOne(10);        // non const object
    const StarWars objTwo(20);      // const object

    objOne.falcon();     // No error
    objTwo.falcon();     // No error

    cout << objOne.i << objTwo.i;

    objOne.gamma();     // No error
    objTwo.gamma();     // Compile time error
}
```

## Usage of & operator
* Bitwise AND
    * The bitwise AND operator (&) compares each bit of the first operand to that bit of the second operand.
      If both bits are 1, the bit is set to 1. Otherwise, the bit is set to 0.
      Both operands to the bitwise AND operator must be of integral types
#### Example C++
  ```c++
  #include <iostream>  
using namespace std;
 
int main() {  
   unsigned short a = 0x5555;      // pattern 0101 ...  
   unsigned short b = 0xAAAA;      // pattern 1010 ...  

   cout << hex << ( a & b ) << endl;
}
  ```
* Address Of operator
    * It is a unary operator that returns the address of the variable(r-value) specified by its operand.
#### Example C++
  ```c++
#include <iostream>
using namespace std;

int main () {
   int  var;
   int  *ptr;

   var = 3000;

   // take the address of var
   ptr = &var;
   cout << "Value of var :" << var << endl;
   cout << "Value of ptr :" << ptr << endl;

   return 0;
} 
```
* Logical AND
#### Example C++
  ```c++
  #include <iostream>  
using namespace std;
 
int main() {  
   int a,b,c;
   a=2;
   b=7;
   c = (a>b) ? a : b ;
   cout << c << '\n';}
  ```
