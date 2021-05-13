## Defining and declaring constants and variables:
This is taken directly from the spec as the 'types' students are expected to know about. This list is alphabetical and unstructured. It has some odd gaps (why **array** and **set** but not **list**?), some ambiguities (**object** as in JavaScript or object as in OOP, **record** as in databases or as in Pascal?), and cheerfully mixes fixed width types with variable length types and simple types with collection types.

+ alphanumeric strings
+ arrays
+  Boolean
+ characters
+ date/time
+ floating point (real)
+ integers
+ objects
+ records
+ sets
+ strings

----

This is a working version with i) obvious omissions added ii) more structure iii) a resolution of ambiguities

### Simple fixed length types

These types can be stored in a fixed number of bits/bytes. The **char** type is implemented very differently in different programming languages and may not even exist. The decimal or currency type also tends to be handled differently in different systems and datetime may be 

+ integer
+ float (real)
+ datetime
+ decimal(currency)
+ boolean
+ char

### Variable length types

These types have a length and will require a number of bytes related to their length. In many systems strings will also have an associated *encoding* which wil affect their length (in bytes)

+ string

### Collection types

+ array
+ list
+ set 
+ dictionary (associative array)

### Complex types

+ record
+ object

The distinction between these is otiose (look it up). Arguably record is a subset of object. A record is generally considered as a collection of data of potentially different types in named 'fields'. Usually a record has a fixed, global definition and cannot be altered in the course of a program.
Objects are often considered as user-defined data types. They also contain fields that may be of any other defined type, but may have different collections of fields at different types and may also contain things that are not simply data, eg executable code ('methods').

## Managing variables:
+ local and global variables

Differ in 'scope'. Can they interact with only one item/object/section of code or with everything in the program?

+ naming conventions

Most languages have ideas about good and bad ways of naming variables (and other things)

maximumValue
MaximumValue
maximum-value
maximum_value

see https://www.python.org/dev/peps/pep-0008/#naming-conventions
