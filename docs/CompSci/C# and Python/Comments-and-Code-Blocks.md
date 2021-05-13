# C# and Python

## Comments and Code Blocks

### Comments

#### C#

##### Line comments

Line comments are introduced with a '//'. Everything from that point until the next NL is ignored.

```C#

//This is a comment
Console.WriteLine("Hello"); // So is this
```

##### Block comments

Block comments are introduced with a /* and terminate with */

```C#
/*
Everything until the end of the comment
is a comment
*/
```

##### Documentation

C# (in Visual Studio!) supports auto documentation via '///' comments. In the approproriate context (immediately *before* a structure) these cause a template to be inserted by Visual Studio that is appropriate to what is being documented. These comments are then converted into an XML file (either internal or as a separate file depending upon Project Properties) which can be further process by documentation tools (e.g. will produce automatic tooltips in Visual Studio or read-and-rendered by the Object Browser)

```C#
///<summary>
/// ... a summary of Fred's purpose 
///<summary>
public class Fred() ...

```

#### Python

##### Line comments

Use a '#' for a line comment in Python

```Python
# This is a comment

```

##### Block comments

Docstrings (see below) are often used for multiline block-comments

##### Documentation

Triple quotes, `'''` or `"""`, may be used to mark the beginning and end of a multi-line string literal. If 'bare', i.e. not used as part of an expression, these generate no code and are equivalent to multi-line comments.

These are traditionally used as DOCSTRINGS immediately *after* the first line of a structure in which case they will be automatically made available via the ```__doc__``` special attribute and used by such things as help.

```Python
class Fred:
''' Fred's docstring starts here 
and goes on
as long as you wish
up to here
'''
    pass
```

### Code Blocks

#### C#

A block of code is surrounded by '{' and '}'
These delimiters are often syntactically unnecessary when a block is a single statement (e.g. an ```if``` or ```for``` governing a single statement).
A block can be introduced at any arbitrary point where you wish to create a new scope.

Statements are multi-line ... in the sense that white space and EOL are ignored ... and terminated by a ```;```

#### Python

A block of code is marked by its indentation. Consequently there are many places in Python source code where indentation/outdentation is *required* it rarely an optional formatting feature.

You may *not* use indents to create arbitrary scope. 

Python will treat any combination of spaces and tabs as creating an indent *but it must then be used consistently until the end of that source file*. Irregular tabbing is a common problem especially when importing and then further editing. Consequently the Python style guide recommends that an indent is always four spaces. Many editors wil replace a tab with four spaces automatically when editing Python.

Statements are terminated by EOL although syntactically incomplete statements continue as required.

A ';' may be used to separate two statements on a single line although there is rarely a need for this and it is likely to confuse.

A ':' must be used to conclude the first line of class and method declarations, if statements and the like.

```Python
class Fred:
    '''
    Note the :
    Note the indent. Everything that follows is part of the class 
    until the next outdent
    '''
    pass
```

Python has the ```pass``` keyword which is a syntactic no-op and can be used where something (a class, a function) requires a body but we wish to provide nothing.
