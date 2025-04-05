# How to comment?

- [How to comment?](#how-to-comment)
  - [Different types of comments](#different-types-of-comments)
  - [Things to avoid when writing comments](#things-to-avoid-when-writing-comments)
  - [Common comment styles](#common-comment-styles)
    - [Javadoc style](#javadoc-style)
      - [Comments in file headers](#comments-in-file-headers)
      - [Comments in data structures](#comments-in-data-structures)
      - [Comments in functions](#comments-in-functions)
      - [Comments in code](#comments-in-code)

## Different types of comments

- comments in file headers: describe what the file contains, and its metadata such as author, date, and license.
- comments in data structures: describe the purpose of the data structure and its usage.
- comments in functions: describe what the function does, its parameters, and its return value.
- comments in code: describe why the code is written in a certain way.

## Things to avoid when writing comments

- Redundant comments: comments that simply restate what the code already makes clear.
- Commenting out code without explanation: do not leave commented-out code without explaining why it was removed or left in place.
- Referring to other comments: avoid referencing other comments within your comment, as it forces developers to hunt through the codebase for context.
- Using comments for task management: avoid leaving "TODO" comments in code; use proper task management tools instead.

## Common comment styles

### Javadoc style

Originally, Javadoc is an API documentation generator for the Java programming language. The content and formatting of a resulting document are controlled via special markup in source code comments. This markup syntax is referred to as Javadoc style comments.

Some C/C++ documentation generators such as Doxygen also use Javadoc style comments to generate documentation from the code.

Javadoc style comments are start with `/**` and end with `*/`. Besides it uses metadata tags `@` to describe the code, such as `@file`, `@author`, `@date`, `@license`, etc. Refer to [Doxygen - Special Commands](https://www.doxygen.nl/manual/commands.html#cmdfile) for more information about tags.

#### Comments in file headers

```cpp
/**
 * @file <filename>
 *
 * <file description>
 *
 * @author <author>
 * @date <date>
 * @license <license>
 */
```

For example, the file header of the `main.cpp` file is:

```cpp
/**
 * @file main.cpp
 *
 * This file contains the main function.
 *
 * @author David
 * @date 2025-04-04
 * @license The code is licensed under the MIT license.
 */
```

#### Comments in data structures

```cpp
/**
 * @brief <struct description>
 *
 * <struct description>
 *
 * @var <field name> <field description>
 */
```

For example, the comment in the `Point` struct is:

```cpp
/**
 * @brief A point in 2D space
 *
 * This struct represents a point in 2D space.
 *
 * @var x The x coordinate of the point
 * @var y The y coordinate of the point
 */
struct Point {
    double x;
    double y;
};
```

#### Comments in functions

```cpp
/**
 * @brief <function description>
 *
 * <function description>
 *
 * @param <parameter name> <parameter description>
 *
 * @return <return value> <return value description>
 */
```

For example, the comment in the `Add` function is:

```cpp
/**
 * @brief Add two numbers
 *
 * This function adds two numbers and returns the result.
 *
 * @param a The first number
 * @param b The second number
 *
 * @return The sum of a and b
 */
int Add(int a, int b) {
    return a + b;
}
```

#### Comments in code

You can just use regular comment syntax to comment in code.

```cpp
// <comment>
```
