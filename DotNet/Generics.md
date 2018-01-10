# Generics
## Design and Implementation of Generics in .NET
In .NET the generics is supported from virtual machine layer not just in compilation alone.
> It is better work for function and types which is handling data or values not depend or based on its type.
### Designing goals
1. Safety : *Bugs are caught at compile time.*
2. Expressivity : *Different specialization using type parameter.*
3. Clarity : *Less casting between types.*
4. Efficiency : *Reduced or no need for run-time checks.* 

### Summary of Design
1. **Polymorphic Declaration** <p>
..to be filled

2. **Runtime Types** <p>
..to be filled

3. **Unrestricted Instantiations** <p>
..to be filled

4. **Bounded Polymorphism** <p>
..to be filled

5. **Polymorphism Inheritance** <p>
..to be filled

6. **Polymorphic Recursion** <p>
..to be filled

7. **Polymorphic Virtual Methods** <p>
..to be filled

### Popular Features Not Supported
- *Higher order type* - Haskell & SML
- *Type class mechanism* - Haskell & Mercury
- *Covariant subtyping on type constructor* - Eiffels
- *Full template like support* - C++

### Final Implementation Summary
1. Just in time.
2. Sharing code and representation.
3. Avoid boxing and unboxing.
4. Efficient run-time support.

### C# Generics and Polymorphism
Examples and use cases of parametric polymorphism in C# generics.

#### 1. Using Parameterized types
**Object based stack**
```csharp
// Definition
class Stack
{
  void push(object value);
  object pop();
}

// Usage
Stack s = new Stack();
s.push(13);
int value = (int)s.pop();
// Above the boxing and unboxing is happened.

// Also belew operation(not type safe) is also possible since no strict type checking.
s.push("string");

```
**Generic stack**
```csharp
// Definition
class Stack<T>
{
  void push(T value);
  T pop();
}

//Usage
Stack<int> s = new Stack<int>();
s.push(13);
int value = s.pop();
// Above the boxing and unboxing is not happening.

// All below operations are illegal.
string val = s.pop();
s.push("string");
```
> In object based approach, we have to cast explicitly as well as it use boxing and unboxing everywhere.

#### 2. Exact Runtime types
As CLR supporting run-time type checks, checked coercions and reflections we have to store the exact run-time type associated with objects.
In C# Generics it enforces us to use exact types in way exact same type parmeter.
```csharp
object obj = new Stack<int>();
Stack<int> s2 = (Statck<int>)obj;          // It succeeds since exact type parameter.
Stack<string> s3 = (Statck<string>) obj;   // It is not supported and thows exception.   
```

#### 3. Polymorphic methods
Methods which can take both normal parameter as well as type parameter. 
eg: Array.Slice<T>() and Array.Reverse<T>() are the static polymorphic methods in Array class.

#### 4. Definition of parmeterized types
- Class 

```csharp
class Stack<T>
{
  void push(T value);
  T pop();
}
```

- Interface

```csharp
interface ISet<T>
{
    bool Contains(T t);
    void Add(T t);
    void Remove(T t);
}
```

- Struct

```csharp
struct Pair<T, U>
{
    public T fst;
    public U snd;

    public Pair(T t, U u)
    {
        fst = t;
        snd = u;
    }
}
```

- Delegates
```csharp
public delegate void Del<T>(T item); 
public static void Notify(int i) { }  
Del<int> m1 = new Del<int>(Notify);
```

### IL Support for Generics
<Insert pic of comparison>
Main changes to the IL are
a. Adding new type to the IL type system.


b. Polymorphic form of declarations.

c. Polymorphism in instructions.
- `ldarg, ldfld, newarr` are already supporting generics.
- Type parmeter is referenced by the number. eg : `Stack<!0>`.
- `box` and `unbox.val` to support <T> to convert from and to Object.
- 

### Interesting Questions
1. Should we  able to convert a `List<string>` to a `List<object>` similar to `Array<string>` casting to `Array<object>`?
    In type-theory terminology, we describe this behavior by saying that C# array types are “covariant” and generic types are “invariant”.  

### Terms
- **Parameterized types** : A type which accepts other types as the parameter.
- **Polymorphic methods** : Methods which can accept the types as well as values and act based on that.
- **Parametric Polymorphism** : Making and working with methods and types generic so that it can handle the data values without depending on the types of the value. eg: Operations like grouping(List, stack, method append)
