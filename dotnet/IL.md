﻿# Intermediate Language for CLR

## Instructions
### 1. ldc
load constant to evaluation stack. *ldc.{type}.value*
eg : `ldc.i4.2` will load value 4 as int32.
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
load constant to evaluation stack. *ldc.{type}.value*
eg : `ldc.i4.2` will load value 4 as int32.
**before**

|Stack Top|
|:-------:|
|   ...   |

**after**

|Stack Top|
|:-------:|
|    4    |
|   ...   |
