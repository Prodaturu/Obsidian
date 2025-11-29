**Created:** 29.11.25, 13:36

**Status:**

**Hashtags:**
- #CPP 
- #templates
- #genericprogramming
- #compiletimepolymorphism
- #advancedcpp
- #metaprogramming

**Links / Tags:** 
- **Relevance Links:**

- **Topic Tags:**


# Templates

**Definition**: Templates allow writing generic code that works with any data type, enabling **compile-time polymorphism**.

**Purpose**: Write once, use with multiple types - avoiding code duplication while maintaining type safety.

---

## 🎯 Core Concept

Templates are like **blueprints** that generate specific code for each data type at compile time.

---

## ⚡ Function Templates

### Basic Syntax

```cpp

template <typename T>
T functionName(T parameter) {
    // Code using type T
}
```

### Practical Example

```cpp

template <typename T>
T getMax(T a, T b) {
    return (a > b) ? a : b;
}

int main() {
    cout << getMax<int>(10, 20);     // Compiler generates getMax for int
    cout << getMax<double>(3.14, 2.99); // Compiler generates getMax for double
    cout << getMax<string>("apple", "banana"); // Works with strings too!
}
```

### Type Deduction (Compiler Magic)

```cpp

getMax(10, 20);     // Compiler deduces T = int
getMax(3.14, 2.99); // Compiler deduces T = double
```


## 🏗️ Class Templates

### Basic Syntax

```cpp

template <typename T>
class ClassName {
    // Members using type T
};
```

### Container Example

```cpp

template <typename T>
class Box {
private:
    T content;
public:
    Box(T value) : content(value) {}
    
    T getValue() { return content; }
    void setValue(T newValue) { content = newValue; }
};

// Usage:
Box<int> intBox(42);           // Box that stores integers
Box<string> stringBox("Hello"); // Box that stores strings
Box<double> doubleBox(3.14);   // Box that stores doubles
```

### Multiple Type Parameters

```cpp

template <typename Key, typename Value>
class Pair {
public:
    Key first;
    Value second;
    
    Pair(Key k, Value v) : first(k), second(v) {}
    
    void display() {
        cout << first << ": " << second << endl;
    }
};
// Usage:
Pair<string, int> person("John", 25);     // Name and age
Pair<int, double> measurement(1, 99.5);   // ID and value
```

## 🔧 Advanced Template Features

### Template Specialisation

```cpp

// Generic version
template <typename T>
class Printer {
public:
    void print(T value) {
        cout << "Value: " << value << endl;
    }
};

// Specialized version for strings
template <>
class Printer<string> {
public:
    void print(string value) {
        cout << "String: \"" << value << "\"" << endl;
    }
};
```

### Default Template Parameters

```cpp

template <typename T = int>  // Default to int if not specified
class Container {
    T value;
public:
    Container(T v) : value(v) {}
};

Container<> defaultContainer(5);    // Uses int (default)
Container<double> doubleContainer(3.14);
```

## 🚀 Real-World Examples

### Generic Array Class

```cpp

template <typename T, int Size = 10>
class Array {
private:
    T elements[Size];
public:
    void set(int index, T value) {
        if (index >= 0 && index < Size)
            elements[index] = value;
    }
    
    T get(int index) {
        return elements[index];
    }
};

Array<int, 5> intArray;        // Integer array of size 5
Array<double> doubleArray;      // Double array of size 10 (default)
```

## 📋 Template Rules & Best Practices

### Do's ✅

- Use descriptive names: `typename ElementType` instead of just `T`
    
- Put templates in header files (.h/.hpp)
    
- Use type deduction when possible
    
- Document template requirements

### Don'ts ❌

- Don't put templates in `.cpp` files (with exceptions)
    
- Don't forget template specialisation needs
    
- Don't over complicate with too many type parameters

### File Organisation

```cpp

// MyTemplate.h
template <typename T>
class MyTemplate {
    // Implementation here (not in .cpp)
};

// No MyTemplate.cpp file needed!
```

## 🎓 Mental Models

**Template = "Code generator that creates specific versions at compile time"**

**Generic Programming = "Algorithms that work across different types"**


## 💡 When to Use Templates

- **Containers**: vectors, lists, arrays that hold any type
    
- **Algorithms**: sorting, searching that work with any data type
    
- **Math operations**: calculations that work with int, float, double
    
- **Smart pointers**: memory management for any type

# References


## Closely Related Notes

### Next:

### Prev:
