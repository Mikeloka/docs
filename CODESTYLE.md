# Indent style

This document explains the codestyle that the Aurora Framework uses. We use this rules to keep our code spaghetti safe and with a better look.

## Aurora Codestyle Specification
<!-- TOC depthFrom:3 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Comments](#comments)
	- [Initial Comments](#initial-comments)
	- [Documentation Comments](#documentation-comments)
	- [Code Comments](#code-comments)
- [Naming](#naming)
	- [Types](#types)
	- [Functions](#functions)
	- [Objects and Variables](#objects-and-variables)
	- [Acronyms](#acronyms)
- [Lines](#lines)
	- [Length](#length)
	- [Ending](#ending)
- [File encoding](#file-encodig)
- [Braces](#braces)
- [Tab idention](#tab-idention)

<!-- /TOC -->

### Comments
In Aurora code files, we have a very well defined anatomy for comment blocks. You have three types of comments: the initial comments, documentation comments and code comments. All of them need to be written in English and well explained for easier development of other programmers that want to contribute to the project.

#### Initial Comments
Initial comments have general information about the file and should be present on ALL source code files. We have a boilerplate for C-like languages and languages that have `#` as 'keyword' for comment blocks. Depending on the license of the repository, you should use GPL-3.0 and LGPL-3.0 boilerplates. You can found it [here](BOILERPLATES.md).


#### Documentation Comments
To compile our documentation we use Doxygen, which uses JavaDoc Style for C-like languages and Doxygen style for other languages as a comment standard for automatically code structure detection. When you write a code file you should use this structure on header files:
```cpp
/** Example comment
 * Another comment
 *
 */
```
or this, in case of a non C-like language:
```cmake
## Example comment
# Another comment
#
```

You should use special commands to Doxygen know what you want to do with this comment. Here is some useful and most used commands:
-   `@file`
-   `@param`
-   `@return`
-   `@see`
-   `@author`

You can find the full list [here](http://www.stack.nl/~dimitri/doxygen/manual/commands.html).

For better codestyle we activated the `JAVADOC_AUTOBRIEF`, which means that you can automatically initialize a brief description ending with a first dot followed by a space or a new line. For example:
```cpp
/** Brief description which ends at this dot. Details follow
 * here.
 */
```
**Note:** Because of the aesthetics, use the brief in the first line (follow the example) whenever possible.

Here is a practical example of a documentation comment:
```cpp
/** Constructs a vector with the given coordinates.
 * @param x The x value for the x coordinate.
 * @param y The y value for the y coordinate.
 * @see Vector2D( )
 * @see Vector2D(float )
 */
```
You can also use single comments for documentation: `///`.

On this comments you should use a formal and clear language, because the purpose of that comments is to automatically create the documentation reference of the framework.

#### Code Comments
This type of comments can be used on on headers and source files. The purpose of that comments is to help people understand an instruction or even a block of code. That use the common syntax of a comment: `//` and:
```cpp
/*
block comments
*/
```
Here you just need to be clear on what you want to explain to the programmer, so no formal language needed and for better communication, use easy words.

### Naming
To name our code we use typical method adopted in programming to know whats the type of the instructions used. We use a different name idention for types, functions and objects/variables.

#### Types
For types such as a `class`, `struct`, `typedef`, `enum`, `namespace`, etc, you should use PascalCase which means that the first letter of each concatenated word is capitalized. Here some examples:

- BackColor
- TimeUtc
- Timer

#### Functions
For functions you should use camelCase which means that the first word is in lowercases and the rest of the words starts with a capital letter. Here some examples:
- `getName()`
- `setName()`
- `isNull()`

#### Objects and Variables
For objects or variables we use all in lowercase. Specifically, for private members use an `_` at the begin.

**Note**: Words that is already assigned by the language (keywords), you should use an `_` at the end.

#### Acronyms
If the first letter is uppercase then the whole acronym should have uppercase letters. Else if the first letter is lowercase then the whole acronym should have lowercase letters. Here some examples:
- `ASCIIArt`
- `asciiArt`

### Lines
Line structure is important for programmers. If lines are separated and with a length limit, code readability is improved and the development workflow is way better. It's important that blank lines exists and may added to separate different blocks of code.

#### Length
When talking about soft limit, the lines should not pass 80 characters. For hard limit, lines must not pass 120 characters.

#### Ending
For line ending we use Unix LF (linefeed). When you are developing on Windows, you should use a linefeed compatible editor.

### File encoding
You must use 8-bit unicode, UTF-8.

### Braces
If its a function, don't open braces in the same line as the declarations, else please open it in the same line. To close braces you must always do it in a new line, unless its has no body.

### Tab idention
Use tab instead of spaces for tab idention and configure your editor for 4 spaces in a single tab. Then, for alignment, use spaces. This helps to reduce the project size.