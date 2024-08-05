Tags: [[C]]

```
int my_array[] = {1,23,6,-5};
int* ptr;
ptr = &my_array[0];
```
now can use ```*(ptr+1)``` , ```*ptr++ vs *(++ptr)```

Standard states these are interchangable
```
ptr = &my_array[0];
ptr = my_array; //name of array is address of first element
```

Generic pointer
```
void* vptr;
```

String in C
```
char my_str[10];
//////////////////////////////////////////////////////////////////
my_str[0] = 'a';
my_str[1] = 'b';
my_str[2] = '\0'; // Binary zero, nul, one byte of memory
//////////////////////////////////////////////////////////////////
my_str[10] = {'a','b','\0'};
//////////////////////////////////////////////////////////////////
my_str[10] = "ab";
```

NULL is the macro for initialize null pointers

```c
char *my_strcpy(char *destination,const char *source) //creates another pointer, const will not modify the contents
// char* &destination does not create another pointer (you can point the original to somewhere else)
{
	char *p = destination;
	while (*source != '\0') // or (*source)
	{
	*p++ = *source++;
	}
	*p = '\0';
	return destination;
	}
```

You can also try ```(char arr1[], char arr2[])``` address of the first element is passed by notation is different, you can use index here as well! ```*(dest+i) equals dest[i]```

```
char my_string[40] = "Ted"; 40 byte array
char my_name[] = "Ted"; 4 byte array, address will not be mov into a register
char *my_name = "Ted"; 4 byte array + address for that array, can be stored anywhere does not need to be in stack
```

```
char multi[5][10];
multi[0] = {'0','1','2','3','4','5','6','7','8','9'}
multi[0][3] = '3';

//in memory will look like 0123456789abcdefgh... because arrays are contiguous
```