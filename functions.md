# Functions

프로그램에서 재사용이 가능한 소스 코드의 일부분을 함수라고 합니다. 함수는 여러 개의 문장에 특별한 이름을 붙인 것이며, 
함수는 프로그램의 어느 곳에서든 정해진 이름으로 블록 안의 문장을 실행할 수 있게 합니다. 이것을 함수의 *호출*이라고 부릅니다.
`len`이나 `range`도 모두 파이썬 표준 라이브러리가 제공하는 함수입니다.

함수라는 개념은 모든 프로그래밍 언어에서 프로그램을 구성하는 가장 중요한 부분이기 때문에, 이번 장에서는 함수의 다양한 특징에 대해 자세히 알아보도록 하겠습니다.

파이썬에서 함수를 정의할 때는 `def` 키워드를 사용합니다. `def` 키워드 다음에는 함수의 이름이 되는 *식별자*와 변수의 이름이 들어갈 수도 있는 소괄호 한 쌍이 오고, 줄의 맨 끝에는 콜론 (`:`)을 붙여줍니다.
그 다음 줄부터는 함수의 내용이 되는 여러 개의 문장이 들어갑니다. 아래의 코드는 함수의 간단한 예제입니다.

Example (save as `function1.py`):

<pre><code class="lang-python">{% include "./programs/function1.py" %}</code></pre>

Output:

<pre><code>{% include "./programs/function1.txt" %}</code></pre>

**How It Works**

We define a function called `say_hello` using the syntax as explained above. This function takes no parameters and hence there are no variables declared in the parentheses. Parameters to functions are just input to the function so that we can pass in different values to it and get back corresponding results.

Notice that we can call the same function twice which means we do not have to write the same code again.

## 함수의 매개 변수 (Function Parameters)

A function can take parameters, which are values you supply to the function so that the function
can *do* something utilising those values. These parameters are just like variables except that the
values of these variables are defined when we call the function and are already assigned values
when the function runs.

Parameters are specified within the pair of parentheses in the function definition, separated by
commas. When we call the function, we supply the values in the same way.  Note the terminology
used - the names given in the function definition are called *parameters* whereas the values you
supply in the function call are called *arguments*.

Example (save as `function_param.py`):

<pre><code class="lang-python">{% include "./programs/function_param.py" %}</code></pre>

Output:

<pre><code>{% include "./programs/function_param.txt" %}</code></pre>

**How It Works**

Here, we define a function called `print_max` that uses two parameters called `a` and `b`.  We find out the greater number using a simple `if..else` statement and then print the bigger number.

The first time we call the function `print_max`, we directly supply the numbers as arguments. In the second case, we call the function with variables as arguments. `print_max(x, y)` causes the value of argument `x` to be assigned to parameter `a` and the value of argument `y` to be assigned to parameter `b`. The `print_max` function works the same way in both cases.

## 지역 변수

When you declare variables inside a function definition, they are not related in any way to other variables with the same names used outside the function - i.e. variable names are *local* to the function. This is called the *scope* of the variable. All variables have the scope of the block they are declared in starting from the point of definition of the name.

Example (save as `function_local.py`):

<pre><code class="lang-python">{% include "./programs/function_local.py" %}</code></pre>

Output:

<pre><code>{% include "./programs/function_local.txt" %}</code></pre>

**How It Works**

The first time that we print the *value* of the name *x* with the first line in the function's body, Python uses the value of the parameter declared in the main block, above the function definition.

Next, we assign the value `2` to `x`. The name `x` is local to our function.  So, when we change the value of `x` in the function, the `x` defined in the main block remains unaffected.

With the last `print` statement, we display the value of `x` as defined in the main block, thereby confirming that it is actually unaffected by the local assignment within the previously called function.

## `global` 문장 {#global-statement}

If you want to assign a value to a name defined at the top level of the program (i.e. not inside any kind of scope such as functions or classes), then you have to tell Python that the name is not local, but it is *global*. We do this using the `global` statement. It is impossible to assign a value to a variable defined outside a function without the `global` statement.

You can use the values of such variables defined outside the function (assuming there is no variable with the same name within the function). However, this is not encouraged and should be avoided since it becomes unclear to the reader of the program as to where that variable's definition is. Using the `global` statement makes it amply clear that the variable is defined in an outermost block.

Example (save as `function_global.py`):

<pre><code class="lang-python">{% include "./programs/function_global.py" %}</code></pre>

Output:

<pre><code>{% include "./programs/function_global.txt" %}</code></pre>

**How It Works**

The `global` statement is used to declare that `x` is a global variable - hence, when we assign a value to `x` inside the function, that change is reflected when we use the value of `x` in the main block.

You can specify more than one global variable using the same `global` statement e.g. `global x, y, z`.

## Default Argument Values {#default-arguments}

For some functions, you may want to make some parameters *optional* and use default values in case the user does not want to provide values for them. This is done with the help of default argument values. You can specify default argument values for parameters by appending to the parameter name in the function definition the assignment operator (`=`) followed by the default value.

Note that the default argument value should be a constant. More precisely, the default argument value should be immutable - this is explained in detail in later chapters. For now, just remember this.

Example (save as `function_default.py`):

<pre><code class="lang-python">{% include "./programs/function_default.py" %}</code></pre>

Output:

<pre><code>{% include "./programs/function_default.txt" %}</code></pre>

**How It Works**

The function named `say` is used to print a string as many times as specified. If we don't supply a value, then by default, the string is printed just once. We achieve this by specifying a default argument value of `1` to the parameter `times`.

In the first usage of `say`, we supply only the string and it prints the string once. In the second usage of `say`, we supply both the string and an argument `5` stating that we want to *say* the string message 5 times.

> *CAUTION*
> 
> Only those parameters which are at the end of the parameter list can be given default argument
> values i.e. you cannot have a parameter with a default argument value preceding a parameter without
> a default argument value in the function's parameter list.
> 
> This is because the values are assigned to the parameters by position. For example,`def func(a,
> b=5)` is valid, but `def func(a=5, b)` is *not valid*.

## Keyword Arguments

If you have some functions with many parameters and you want to specify only some of them, then you can give values for such parameters by naming them - this is called *keyword arguments* - we use the name (keyword) instead of the position (which we have been using all along) to specify the arguments to the function.

There are two advantages - one, using the function is easier since we do not need to worry about the order of the arguments. Two, we can give values to only those parameters to which we want to, provided that the other parameters have default argument values.

Example (save as `function_keyword.py`):

<pre><code class="lang-python">{% include "./programs/function_keyword.py" %}</code></pre>

Output:

<pre><code>{% include "./programs/function_keyword.txt" %}</code></pre>

**How It Works**

The function named `func` has one parameter without a default argument value, followed by two parameters with default argument values.

In the first usage, `func(3, 7)`, the parameter `a` gets the value `3`, the parameter `b` gets the value `7` and `c` gets the default value of `10`.

In the second usage `func(25, c=24)`, the variable `a` gets the value of 25 due to the position of the argument. Then, the parameter `c` gets the value of `24` due to naming i.e. keyword arguments. The variable `b` gets the default value of `5`.

In the third usage `func(c=50, a=100)`, we use keyword arguments for all specified values. Notice that we are specifying the value for parameter `c` before that for `a` even though `a` is defined before `c` in the function definition.

## VarArgs parameters

Sometimes you might want to define a function that can take _any_ number of parameters, i.e. **var**iable number of **arg**uments, this can be achieved by using the stars (save as `function_varargs.py`):

<pre><code class="lang-python">{% include "./programs/function_varargs.py" %}</code></pre>

Output:

<pre><code>{% include "./programs/function_varargs.txt" %}</code></pre>

**How It Works**

When we declare a starred parameter such as `*param`, then all the positional arguments from that point till the end are collected as a tuple called 'param'.

Similarly, when we declare a double-starred parameter such as `**param`, then all the keyword arguments from that point till the end are collected as a dictionary called 'param'.

We will explore tuples and dictionaries in a [later chapter](./data_structures.md#data-structures).

## `return` 문장 {#return-statement}

The `return` statement is used to *return* from a function i.e. break out of the function. We can optionally *return a value* from the function as well.

Example (save as `function_return.py`):

<pre><code class="lang-python">{% include "./programs/function_return.py" %}</code></pre>

Output:

<pre><code>{% include "./programs/function_return.txt" %}</code></pre>

**How It Works**

The `maximum` function returns the maximum of the parameters, in this case the numbers supplied to the function. It uses a simple `if..else` statement to find the greater value and then *returns* that value.

Note that a `return` statement without a value is equivalent to `return None`. `None` is a special type in Python that represents nothingness. For example, it is used to indicate that a variable has no value if it has a value of `None`.

Every function implicitly contains a `return None` statement at the end unless you have written your own `return` statement. You can see this by running `print(some_function())` where the function `some_function` does not use the `return` statement such as:

```python
def some_function():
    pass
```

The `pass` statement is used in Python to indicate an empty block of statements.

> TIP: There is a built-in function called `max` that already implements the 'find maximum' functionality, so use this built-in function whenever possible.

## 코드의 문서화

Python has a nifty feature called *documentation strings*, usually referred to by its shorter name *docstrings*. DocStrings are an important tool that you should make use of since it helps to document the program better and makes it easier to understand. Amazingly, we can even get the docstring back from, say a function, when the program is actually running!

Example (save as `function_docstring.py`):

<pre><code class="lang-python">{% include "./programs/function_docstring.py" %}</code></pre>

Output:

<pre><code>{% include "./programs/function_docstring.txt" %}</code></pre>

**How It Works**

A string on the first logical line of a function is the *docstring* for that function. Note that DocStrings also apply to [modules](./modules.md#modules) and [classes](./oop.md#oop) which we will learn about in the respective chapters.

The convention followed for a docstring is a multi-line string where the first line starts with a capital letter and ends with a dot. Then the second line is blank followed by any detailed explanation starting from the third line. You are *strongly advised* to follow this convention for all your docstrings for all your non-trivial functions.

We can access the docstring of the `print_max` function using the `__doc__` (notice the *double underscores*) attribute (name belonging to) of the function. Just remember that Python treats *everything* as an object and this includes functions. We'll learn more about objects in the chapter on [classes](./oop.md#oop).

If you have used `help()` in Python, then you have already seen the usage of docstrings! What it does is just fetch the `__doc__` attribute of that function and displays it in a neat manner for you. You can try it out on the function above - just include `help(print_max)` in your program. Remember to press the `q` key to exit `help`.

Automated tools can retrieve the documentation from your program in this manner. Therefore, I *strongly recommend* that you use docstrings for any non-trivial function that you write. The `pydoc` command that comes with your Python distribution works similarly to `help()` using docstrings.

## Summary

We have seen so many aspects of functions but note that we still haven't covered all aspects of them. However, we have already covered most of what you'll use regarding Python functions on an everyday basis.

Next, we will see how to use as well as create Python modules.
