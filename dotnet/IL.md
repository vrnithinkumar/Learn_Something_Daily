# Intermediate Language for CLR
## Common Abbreviations
- **ld**   : load
- **st**   : set
- **fld**  : field
- **arg**  : argument
- **loc**  : local variable
- **arr**  : array
- **conv** : convert


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

