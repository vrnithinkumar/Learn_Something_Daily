# Git Notes
## Git Internals
Think git as a *Stupid content tracker*. It is also a persistent map. 
## SHA1 to Identify Objects
- It uses SHA1 hash to create hash for the every object it tracks. eg for files, folders.
    - eg : "nithin" => "8e017de300aa8a1b37b30790baf6083b1587a4e9" 
    - 40 character is the hash length.
    - Collision chance is very very rare. 
## How Git Stores 
it stores everything under `.git` folder. 
.git
 |-> objects  *Here is we store evry object under the hash we generated*
        |-> 

blob - generic data

## Links for reference
1. [Pluralsight Git Internals pdf](https://github.com/pluralsight/git-internals-pdf)
