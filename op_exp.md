# 연산자와 수식 {#op-exp}

프로그램에 들어가는 대부분의 문장에는 `2 + 3`과 같은 수식 (expressions)이 들어있습니다. 가장 간단한 수식은 `5`와 같이 하나의 상수와 변수로 이루어져 있는 수식입니다.
수식은 `2`나 `3`처럼 연산의 대상이 되는 값을 의미하는 피연산자 (operand)와 `+` 같은 연산 기호를 뜻하는 연산자 (operator)의 조합으로 이루어집니다.

## 연산자

이제 파이썬의 다양한 연산자에 대해 알아보도록 하겠습니다.

예시로 나온 모든 수식은 파이썬 인터프리터에서 바로 실행하고 결과를 확인해보실 수 있습니다.
예를 들어, 수식 `2 + 3`의 결과값을 확인하려면, 파이썬 인터프리터에서 아래와 같이 수식을 그대로 입력하시면 됩니다.

```python
>>> 2 + 3
5
>>> 3 * 5
15
>>>
```

파이썬 3에서 사용할 수 있는 연산자는 다음과 같습니다.

- `+`
    - 두 수 또는 두 개의 문자열을 더합니다.
    - `3 + 5`의 결과값은 `8`이고, `'a' + 'b'`의 결과값은 `'ab'`입니다.

- `-`
    - 첫 번째 수에서 두 번째 수를 뺍니다.
    - `-5.2`의 결과값은 `-5.2`이고, `50 - 24`의 결과값은 `26`입니다.

- `*`
    - 두 수를 곱하거나 문자열을 정해진 횟수만큼 반복합니다.
    - `2 * 3`의 결과값은 `6`이고, `'la' * 3`의 결과값은 `'lalala'`입니다.

- `**` (제곱 연산자)
    - 첫 번째 수를 `x`, 두 번째 수를 `y`라고 할 때, `x`를 `y` 제곱합니다.
    - `3 ** 4`의 결과값은 `3 * 3 * 3 * 3`, 즉 `81`입니다.

- `/` 
    - 첫 번째 수를 두 번째 수로 나눕니다.
    - `13 / 3`의 결과값은 `4.333333333333333`입니다.

- `//` (나눗셈 후 버림 연산자)
    - 첫 번째 수를 `x`, 두 번째 수를 `y`라고 할 때, `x`를 `y`로 나누고 결과값의 소수점은 버립니다. `x`와 `y` 둘 중에 하나가 부동 소수형 데이터이면 결과값은 부동 소수형 데이터가 됩니다.
    - `13 // 3`의 결과값은 `4`이고,
    - `-13 // 3`의 결과값은 `-5`,
    - `9 // 1.81`의 결과값은 `4.0`입니다.

- `%` (나머지 연산자, modulo 연산자)
    - 두 수를 나누었을 때의 나머지를 구합니다.
    - `13 % 3` gives `1`. `-25.5 % 2.25` gives `1.5`.

- `<<` 
    - Shifts the bits of the number to the left by the number of bits specified. (Each number is represented in memory by bits or binary digits i.e. 0 and 1)
    - `2 << 2` gives `8`. `2` is represented by `10` in bits.
    - Left shifting by 2 bits gives `1000` which represents the decimal `8`.

- `>>`
    - Shifts the bits of the number to the right by the number of bits specified.
    - `11 >> 1` gives `5`.
    - `11` is represented in bits by `1011` which when right shifted by 1 bit gives `101`which is the decimal `5`.

- `&`
    - Bit-wise AND of the numbers
    - `5 & 3` gives `1`.

- `|`
    - Bitwise OR of the numbers
    - `5 | 3` gives `7`

- `^`
    - Bitwise XOR of the numbers
    - `5 ^ 3` gives `6`

- `~`
    - The bit-wise inversion of x is -(x+1)
    - `~5` gives `-6`. More details at http://stackoverflow.com/a/11810203

- `<`
    - Returns whether x is less than y. All comparison operators return `True` or `False`. Note the capitalization of these names.
    - `5 < 3` gives `False` and `3 < 5` gives `True`.
    - Comparisons can be chained arbitrarily: `3 < 5 < 7` gives `True`.

- `>`
    - Returns whether x is greater than y
    - `5 > 3` returns `True`. If both operands are numbers, they are first converted to a common type. Otherwise, it always returns `False`.

- `<=`
    - Returns whether x is less than or equal to y
    - `x = 3; y = 6; x <= y` returns `True`

- `>=`
    - Returns whether x is greater than or equal to y
    - `x = 4; y = 3; x >= 3` returns `True`

- `==`
    - Compares if the objects are equal
    - `x = 2; y = 2; x == y` returns `True`
    - `x = 'str'; y = 'stR'; x == y` returns `False`
    - `x = 'str'; y = 'str'; x == y` returns `True`

- `!=`
    - Compares if the objects are not equal
    - `x = 2; y = 3; x != y` returns `True`

- `not` (논리 NOT 연산자)
    - If x is `True`, it returns `False`. If x is `False`, it returns `True`.
    - `x = True; not x` returns `False`.

- `and` (논리 AND 연산자)
    - `x and y` returns `False` if x is `False`, else it returns evaluation of y
    - `x = False; y = True; x and y` returns `False` since x is False. In this case, Python will not evaluate y since it knows that the left hand side of the 'and' expression is `False` which implies that the whole expression will be `False` irrespective of the other values. This is called short-circuit evaluation.

- `or` (논리 OR 연산자)
    - If x is `True`, it returns True, else it returns evaluation of y
    - `x = True; y = False; x or y` returns `True`. Short-circuit evaluation applies here as well.

## 산술 연산과 대입 연산 합치기

It is common to run a math operation on a variable and then assign the result of the operation back to the variable, hence there is a shortcut for such expressions:

```python
a = 2
a = a * 3
```

can be written as:

```python
a = 2
a *= 3
```

Notice that `var = var operation expression` becomes `var operation= expression`.

## 연산자의 우선순위 {#order-of-evaluation}

If you had an expression such as `2 + 3 * 4`, is the addition done first or the multiplication? Our high school maths tells us that the multiplication should be done first. This means that the multiplication operator has higher precedence than the addition operator.

The following table gives the precedence table for Python, from the lowest precedence (least binding) to the highest precedence (most binding). This means that in a given expression, Python will first evaluate the operators and expressions lower in the table before the ones listed higher in the table.

The following table, taken from the [Python reference manual](http://docs.python.org/3/reference/expressions.html#operator-precedence), is provided for the sake of completeness. It is far better to use parentheses to group operators and operands appropriately in order to explicitly specify the precedence. This makes the program more readable. See [Changing the Order of Evaluation](#changing-order-of-evaluation) below for details.

- `lambda` : Lambda Expression
- `if - else` : Conditional expression
- `or` : Boolean OR
- `and` : Boolean AND
- `not x` : Boolean NOT
- `in, not in, is, is not, <, <=, >, >=, !=, ==` : Comparisons, including membership tests and identity tests
- `|` : Bitwise OR
- `^` : Bitwise XOR
- `&` : Bitwise AND
- `<<, >>` : Shifts
- `+, -` : Addition and subtraction
- `*, /, //, %` : Multiplication, Division, Floor Division and Remainder
- `+x, -x, ~x` : Positive, Negative, bitwise NOT
- `**` : Exponentiation
- `x[index], x[index:index], x(arguments...), x.attribute` : Subscription, slicing, call, attribute reference
- `(expressions...), [expressions...], {key: value...}, {expressions...}` : Binding or tuple display, list display, dictionary display, set display

The operators which we have not already come across will be explained in later chapters.

Operators with the _same precedence_ are listed in the same row in the above table. For example, `+` and `-` have the same precedence.

## 연산자 우선순위 바꾸기 {#changing-order-of-evaluation}

괄호를 사용하면 수식을 더 읽기 편하게 만들 수 있습니다. 괄호가 들어간 수식 `2 + (3 * 4)`는 수식 `2 + 3 * 4`보다 이해하기 쉽다는 것을 알 수 있습니다. 
괄호는 지나치게 복잡하게 넣지 않아야 하고, `(2 + (3 * 4))`처럼 필요없는 괄호를 넣지 않는 것이 좋습니다.

괄호를 사용하면서 얻게 되는 또다른 장점은 바로 괄호가 연산자의 우선순위를 바꾸게 해줄 수 있다는 것입니다. 
For example, if you want addition to be evaluated before multiplication in an expression, then you can write something like `(2 + 3) * 4`.

## 연산자의 결합 규칙 {#associativity}

Operators are usually associated from left to right. This means that operators with the same precedence are evaluated in a left to right manner. For example, `2 + 3 + 4` is evaluated as `(2 + 3) + 4`.

## 수식

Example (save as `expression.py`):

```python
length = 5
breadth = 2

area = length * breadth
print('Area is', area)
print('Perimeter is', 2 * (length + breadth))
```

Output:

```
$ python expression.py
Area is 10
Perimeter is 14
```

**How It Works**

The length and breadth of the rectangle are stored in variables by the same name. We use these to calculate the area and perimeter of the rectangle with the help of expressions. We store the result of the expression `length * breadth` in the variable `area` and then print it using the `print` function. In the second case, we directly use the value of the expression `2 * (length + breadth)` in the print function.

Also, notice how Python _pretty-prints_ the output. Even though we have not specified a space between `'Area is'` and the variable `area`, Python puts it for us so that we get a clean nice output and the program is much more readable this way (since we don't need to worry about spacing in the strings we use for output). This is an example of how Python makes life easy for the programmer.

## 요약

이번 장에서는 프로그램을 만들 때 꼭 필요한 연산자, 피연산자와 수식에 대해 알아보았습니다. Next, we will see how to make use of these in our programs using statements.
