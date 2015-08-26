## R语言中的匿名函数
When you don’t give a name to a function, you are creating an anonymous function. How is this possible? This is because in R a function (any object in fact) is evaluated without the need to assign it or its result to any named variable (we already noted this above, see the second note after the first example) and may in fact apply to any standard R function.
The syntax is slightly different form the ordinary UDF seen above because now you have a different parentheses approach:
First, you employ () as usual, to denote a call to a function, immediately after the keyword ‘function': this may specify the argument, in the example ‘x';
Secondly, a ( ) couple encircles the function(x) declaration and body
Third, after the previous construct you specify the argument passed in the call
It works like this:

### 匿名函数
```
# Anonymous function syntax
(function(x) x * 10)(10)
```

### 正常函数
```
# equivalent (normal) way
fun<-function(x) x * 10
fun(10)
```
