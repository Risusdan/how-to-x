# How to follow a naming convention?

- [How to follow a naming convention?](#how-to-follow-a-naming-convention)
  - [What is a naming convention?](#what-is-a-naming-convention)
  - [Types of naming conventions](#types-of-naming-conventions)
  - [How to choose a naming convention?](#how-to-choose-a-naming-convention)
  - [Google C++ Style Guide](#google-c-style-guide)
    - [File Names](#file-names)
    - [Type Names (Classes, Structs, Type Aliases, Enums)](#type-names-classes-structs-type-aliases-enums)
    - [Variable Names](#variable-names)
    - [Constant Names](#constant-names)
    - [Function Names](#function-names)
    - [Namespace Names](#namespace-names)
    - [Macro Names](#macro-names)
  - [Python PEP 8 Style Guide](#python-pep-8-style-guide)
    - [Package and Module Names](#package-and-module-names)
    - [Class Names](#class-names)
    - [Function and Variable Names](#function-and-variable-names)
    - [Method Names and Instance Variables](#method-names-and-instance-variables)
    - [Constants](#constants)

## What is a naming convention?

A naming convention is a set of rules for naming variables, functions, and other identifiers.

There are many naming conventions depending on the programming language. For example:

- (C/C++) Google C++ Style Guide
- (Python) PEP 8
- (C#) Microsoft C# Style Guide

## Types of naming conventions

- CamelCase: start with lowercase letter and capitalize each new word, e.g. `myVariable`, `myUsefulClass`
- PascalCase: start with uppercase letter and capitalize each new word, e.g. `MyVariable`, `MyUsefulClass`
- snake_case: all lowercase with underscores between words, e.g. `my_variable`, `my_useful_class`
- Hungarian notation: prefix variable with type, e.g. `int iMyVar`, `double dMyVar`

## How to choose a naming convention?

There are always debates about which naming convention is the best. Just choose one you prefer and be consistent within your project.

But there are some general rules that you should follow:
1. Never use `l` (lowercase letter el), `O` (uppercase letter oh), or `I` (uppercase letter eye) as single-character names because they are too similar to `1` and `0`
2. Avoid using names that are too general or ambiguous
3. Avoid using double underscores because they are probably reserved for special names or built-in variables

## Google C++ Style Guide

In C++ the most common naming convention is to follow what Google C++ Style Guide recommends.

### File Names

- All lowercase
- Underscores for word separation
- End in `.cc` for source files and `.h` for headers
- Example: `my_useful_class.cc`

### Type Names (Classes, Structs, Type Aliases, Enums)

- Start with capital letter and capitalize each new word (PascalCase)
- No underscores
- Example: `MyClass`, `MyUsefulClass`

### Variable Names

- All lowercase and underscores between words (snake_case)
- Private class member variables have trailing underscore (underscore at the end of the variable name)
- Example: 
  - Regular variables: `my_variable`, `table_name`
  - Private class member variables: `class_member_`, `table_name_`
  - Public class member variables: `class_member`, `table_name`
  - Struct members: `struct_member`

### Constant Names

- Start with 'k' followed by mixed case
- Example: `kDaysInAWeek`, `kMaximumElements`

### Function Names

- Start with capital letter and capitalize each new word (PascalCase)
- Example: `AddTableEntry()`, `DeleteUrl()`
- Getters and setters match variable names:
  ```cpp
  class MyClass {
    public:
      int count() const { return count_; }
      void set_count(int count) { count_ = count; }
    private:
      int count_;
  };
  ```

### Namespace Names

- All lowercase and underscores between words (snake_case)
- Example: `my_namespace`, `project_namespace`

### Macro Names

- All uppercase and underscores between words
- Example: `MY_MACRO`, `ROUND_UP`

## Python PEP 8 Style Guide

PEP 8 stands for Python Enhancement Proposal 8. It is Python's official style guide. Here are its naming conventions:

### Package and Module Names

- All lowercase with underscores between words (snake_case)
- Example: `my_package`, `requests`

### Class Names

- CapitalizedWords (PascalCase)
- Example: `MyClass`, `RequestHandler`

### Function and Variable Names

- All lowercase with underscores between words (snake_case)
- Example: `my_function`, `my_variable`

### Method Names and Instance Variables

- Same as function names: lowercase with underscores between words (snake_case)
- Use one leading underscore for non-public methods and instance variables
- Use two leading underscores for name mangling
- Example:
  ```python
  class MyClass:
      def my_method(self):          # Public method
          self.my_variable = 1      # Public instance variable
          self._private = 2         # Non-public instance variable
          self.__mangled = 3        # Name-mangled instance variable
  ```

> What is name mangling?
> 
> Name mangling is a process in Python that changes the name of the variables and methods to make them more secure and private. It is done by adding a prefix to the name of the variable or method.

### Constants

- All uppercase with underscores between words (snake_case)
- Example: `MAX_VALUE`, `TOTAL_COUNT`
