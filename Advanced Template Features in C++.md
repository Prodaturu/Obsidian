**Created:** 03.12.25, 10:03

**Status:** #atomic

**Hashtags:**

- #cpp
- #templates
- #genericprogramming
- #advancedcpp  
- #atomic 

**Links / Tags:**

- **Relevance Links:**
    - Templates in C++ <!-- parent, plain text on purpose -->
    - [[Function Templates in C++]]
    - [[Class Templates in C++]]
    - Template and Generic Types in C++
      
- **Topic Tags:**
    
    - #templatespecialisation
    - #defaulttemplateparameters
    - #advancedtemplates


# Advanced Template Features in C++

> Part of templates in C++.

- Advanced template features let you **tune behaviour** for specific types.
    
- Common tools:
    
    - **template specialisation**
    - **default template parameters**


## Template Specialisation

- Template specialisation lets you override the generic template for a specific type.

### Class template specialisation

```cpp
// Generic version
template <typename T>
class Printer
{
public:
    void print(T value)
    {
        cout << "Value: " << value << endl;
    }
};

// Specialised version for string
template <>
class Printer<string>
{
public:
    void print(string value)
    {
        cout << "String: \"" << value << "\"" << endl;
    }
};
```

```cpp
int main()
{
    Printer<int> intPrinter;
    Printer<string> stringPrinter;
    intPrinter.print(42);           // uses generic version
    stringPrinter.print("hello");   // uses specialised version
}
```

#### Key ideas:

- Generic template covers **most** types.
- Specialisation is used when a **particular type** needs different behaviour.
- Overusing specialisation can make code harder to follow, so use it when it really adds clarity.
  
## Partial Specialisation (class templates only)

- You can also specialise **some** template parameters and keep others generic
  
```cpp
// Generic
template <typename T, typename U>
class PairWrapper
{
    // generic implementation
};

// Partial specialisation when both types are the same
template <typename T>
class PairWrapper<T, T>
{
    // specialised implementation for (T, T)
};
```

## Default Template Parameters

- You can give template parameters **default types**, making templates easier to use
  
```cpp
template <typename T = int>
class Container
{
private:
    T value;

public:
    Container(T v) : value(v) {}

    T get() const { return value; }
};
```

```cpp
int main()
{
	Container<> defaultContainer(5);          // uses T = int (default)
    Container<double> doubleContainer(3.14);
    cout << defaultContainer.get() << endl;   // 5
    cout << doubleContainer.get() << endl;    // 3.14
}
```

#### Key ideas:

- Defaults reduce noise when a “usual” type is common.
- You can still override the default explicitly when needed.

---

## When to reach for these features

- Use **specialisation** when one or a few types need **different behaviour**.
- Use **partial specialisation** for a whole family of types with a shared pattern.
- Use **default parameters** when there is a clear “most common” type and you want a simple syntax.

# References
