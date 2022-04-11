# Clean Code

"Clean code" is one of must-have skills every software engineer has to get. However, it is a long journey and need a lot of practices to form a habit of coding clean. A well-known book named "Clean Code" is "must-read" for all of SEs, and this note will list all main ideas of "Clean Code" that I 've absorted after reading that book.

## Naming Convention
1. Should name variables and functions meaningfully
2. Names must to be apprepriate to the context of variables or functions
	 - examples:  String[] ~~lstNameOfStudents~~ = new String[10];
	 - this variable is an array so its name should be arrNameOfStudents
## Writing a proper function
1. A function should be no more than 20 lines
2.  A function do only 1 thing
3.  As few number of arguments as possible, if a function has more than 3 arguments, considering to wrap related arguments into a object
4. Have no side effect (Function does some unexpected behaviours that change variables outside of scope or change system status)
5.  Avoid output parameter 
	- example: void appendFooter(StringBuffer report), this function return nothing but eventually change the value of input parameter. We should avoid this coding style and turn it into: report.appendFooter() to change their own properties of its object.
6. Do not duplicate code

## Comment
1. Do not make redundant comments
2. Do not comment when you can use a function or a variable (naming function and variable properly helps code more readable)
3. Do not add javadoc on private function

## Object and Data Structure
1. Should not set accessor to public or default (only public when needed)
2. DTO is a data structure so it should not include business function

## Error Handling
1. Prefer to use unchecked exception:
When throwing a checked exception, every method calling to it has to catch that type of exception and whenever we change or add new exception type, all related classes have to change as well
Only when you write a critical library or important code block, a checked exception you should consider to use
2. Provide as comprehensive error messages as possible to trace error cause more easily 
3. Often a single exception class is fine for a particular area of code. The information is sent with the exception can distinguish the errors. Using different classes only if there are times when you want to catch one exception and allow the other one to pass through.
4. Limit returning null, if possible, return DEFAULT_VALUE instead

## Class
1. Order of variable types: 
	public static final -> private static -> private 
2. First Class should be small, second Class should be smaller
3. SRP (Single Responsibility Principle)
