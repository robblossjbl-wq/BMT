# BMT Language Grammar Specification

## Formal Grammar (EBNF)

```ebnf
program         = header statement_list endline
header          = "<BMT.V" version ":"
version         = digit "." digit "." digit
statement_list  = { statement }
statement       = assignment
                | function_def
                | class_def
                | if_statement
                | while_loop
                | for_loop
                | return_stmt
                | expression
                | import_stmt
                | try_except

assignment      = identifier "=" expression
expression      = or_expr
or_expr         = and_expr { "or" and_expr }
and_expr        = comparison { "and" comparison }
comparison      = additive { comp_op additive }
comp_op         = "==" | "!=" | "<" | ">" | "<=" | ">="
additive        = multiplicative { add_op multiplicative }
add_op          = "+" | "-"
multiplicative  = unary { mul_op unary }
mul_op          = "*" | "/" | "%" | "//"
unary           = [ "-" | "not" ] power
power           = primary [ "**" unary ]
primary         = literal
                | identifier
                | function_call
                | "(" expression ")"
                | list_literal
                | dict_literal

function_def    = "def" identifier "(" param_list ")" ":" block
param_list      = [ identifier { "," identifier } ]
block           = INDENT statement_list DEDENT

function_call   = identifier "(" arg_list ")"
arg_list        = [ expression { "," expression } ]

if_statement    = "if" expression ":" block
                  { "elif" expression ":" block }
                  [ "else" ":" block ]

while_loop      = "while" expression ":" block
                  [ "else" ":" block ]

for_loop        = "for" identifier "in" expression ":" block
                  [ "else" ":" block ]

return_stmt     = "return" [ expression ]

class_def       = "class" identifier [ "(" identifier ")" ] ":" block

import_stmt     = "import" identifier
                | "from" identifier "import" identifier

try_except      = "try" ":" block
                  { "except" [ identifier [ "as" identifier ] ] ":" block }
                  [ "finally" ":" block ]

literal         = number | string | boolean | none
number          = integer | float
integer         = [ "-" ] digit { digit }
float           = [ "-" ] digit { digit } "." digit { digit }
string          = '"' { char } '"' | "'" { char } "'"
boolean         = "True" | "False"
none            = "None"

list_literal    = "[" [ expression { "," expression } ] "]"
dict_literal    = "{" [ key_value { "," key_value } ] "}"
key_value       = expression ":" expression

identifier      = letter { letter | digit | "_" }
digit           = "0" | "1" | "2" | "3" | "4" | "5" | "6" | "7" | "8" | "9"
letter          = "a" | "b" | ... | "z" | "A" | "B" | ... | "Z"
char            = letter | digit | symbol | " "

endline         = "<endline:" digit { digit } ":" "->"
```

## Token Types

```
KEYWORD:     if, elif, else, for, while, def, class, return, import, from, 
             try, except, finally, True, False, None, and, or, not, break, 
             continue, pass, in, as

OPERATOR:    +, -, *, /, %, //, **, ==, !=, <, >, <=, >=, =, :, ,, ., 
             (, ), [, ], {, }

IDENTIFIER:  [a-zA-Z_][a-zA-Z0-9_]*

NUMBER:      [0-9]+ | [0-9]+\.[0-9]+

STRING:      "[^"]*" | '[^']*'

COMMENT:     #.*

INDENT:      increased indentation

DEDENT:      decreased indentation
```

## Example Programs

### Hello World
```bmt
<BMT.V.1.0.0:
print("Hello, World!")
<endline:1:->
```

### Variables and Types
```bmt
<BMT.V.1.0.0:
name = "John"
age = 30
height = 5.9
is_student = False
items = [1, 2, 3]
person = {"name": "John", "age": 30}
<endline:7:->
```

### Control Flow
```bmt
<BMT.V.1.0.0:
x = 10

if x > 5:
    print("x is greater than 5")
elif x == 5:
    print("x is equal to 5")
else:
    print("x is less than 5")

for i in range(5):
    print(i)

while x > 0:
    print(x)
    x = x - 1
<endline:16:->
```

### Functions
```bmt
<BMT.V.1.0.0:
def add(a, b):
    return a + b

def greet(name):
    print("Hello, " + name + "!")

result = add(5, 3)
print(result)
greet("Alice")
<endline:10:->
```

### Classes
```bmt
<BMT.V.1.0.0:
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    def introduce(self):
        print("I am " + self.name)

person = Person("Bob", 25)
person.introduce()
<endline:11:->
```
