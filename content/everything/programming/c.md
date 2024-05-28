---
title: C
draft: false
tags:
  - programming
---
 Video link: https://www.youtube.com/watch?v=j-_s8f5K30I
## Declaring Variables

A declaration consists of a type and a list of variables as shown below:

```c
main(){
	int lower, upper, step;
	float fahr, celsius;
}
```

Here we declare 3 variables that will contain integers, `lower`, `upper`, and `step`. Then we declare two variables that will contain floating point numbers, `fahr` and `celsius`. 

- ints can be between -32768 and +32767, they are a signed 16-bit number
- floats are 32-bits and can be between 10^-38 and 10^+38
### Other Var Types
| Type   | Description            |
| ------ | ---------------------- |
| char   | a 1 byte character     |
| short  | short int              |
| long   | long int               |
| double | double precision float |

## While Loops
```c
while(i < j){
	i = 2 * i;
}
```

## Difference Between Constants and Variables 
Constant = a fixed value, does not change
Variable = can change over time

### Declaring a constant
```c
#define LOWER 0
```

## Useful Programs
### getchar()
- gets the next input character each time it is called
In the example below `c` will contain character that was inputed.
```c
char c
c = getchar()
```

### putchar()
- writes a character to stdout.
```c
putchar(c)
```

