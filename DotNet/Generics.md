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
> Object based approach has we have to cast explicitly as well as it use boxing and unboxing everywhere.
### Terms
- **Parameterized types** : A type which accepts other types as the parameter.
- **Polymorphic methods** : Methods which can accept the types as well as values and act based on that.
- **Parametric Polymorphism** : Making and working with methods and types generic so that it can handle the data values without depending on the types of the value. eg: Operations like grouping(List, stack, method append)
