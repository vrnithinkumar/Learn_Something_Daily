# Intermediate Language for CLR
- It is stack based.
- It is object oriented.

## Common Abbreviations
- **ld**   : load
- **st**   : set
- **fld**  : field
- **arg**  : argument
- **loc**  : local variable
- **arr**  : array
- **conv** : convert
- **elem** : element
- **br**   : branch

Above abbreviations is pretty much enough to understand difference IL instructions. 

## Instructions
### 1. ldc
load constant to evaluation stack. *ldc.{type}.value*
eg : `ldc.i4.2` will load value 4 as int32.

*Change in stack*

**before**

|Stack Top|
|:-------:|
|   ...   |

**after**

|Stack Top|
|:-------:|
|    4    |
|   ...   |

### 2. ldarg
load argument to evaluation stack. *ldarg.{argument index}*
eg : `ldarg.0` will load 0-th argument to the stack.
> for instance method 0th argumnet will be always `this`.
**before**

|Stack Top|
|:-------:|
|   ...   |

**after**

|Stack Top|
|:-------:|
|    4    |
|   ...   |

## Reference 
1. [ldloc.0 after stloc.0 ](https://stackoverflow.com/questions/44733675/why-there-is-a-ldloc-0-just-after-stloc-0-in-il-code)
2. [Wikipedia list of all instructions](https://en.wikipedia.org/wiki/List_of_CIL_instructions)
