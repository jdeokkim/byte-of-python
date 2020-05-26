# 파이썬 기초 지식

3장에서는 `hello world`만을 출력하는 간단한 프로그램을 만들어 보았지만, 이번에는 상수와 변수 같은 다양한 개념을 배워 보고 `hello world` 이외의 다른 문자열을 출력하는 방법을 배워보겠습니다.

## 주석 {#comments}

주석은 보통 `#` 뒤에 오는 문자열을 가리키며, 다른 사람들이 프로그램을 쉽게 이해할 수 있도록 하기 위해 사용합니다.

다음은 주석의 사용 예입니다.

```python
print('hello world') # print()는 문자열을 화면에 표시한다.
```

```python
# print()는 문자열을 화면에 표시한다.
print('hello world')
```

주석은 주로 이런 경우에 많이 사용합니다.

- `"이 부분은 프로그램이 실행되면 이렇게 되겠지"` 같은 가정에 대해 자세히 적어놓고 싶을 때
- 문제 해결 중에 내린 중요한 결정이나 세부적인 내용을 설명할 필요가 있을 때
- 프로그램을 짜다가 막히는 부분을 적어놓고 싶을 때

[*"코드는 어떻게 하는지를 알려주지만, 주석은 왜 그렇게 하는지를 알려주어야 한다."*](http://www.codinghorror.com/blog/2006/12/code-tells-you-how-comments-tell-you-why.html)

주석은 작성한 프로그램을 다른 사람들이 보았을 때 그 내용을 쉽게 이해할 수 있도록 합니다. 프로그램을 몇 달 뒤에 다시 봤을 때 이해가 잘 안될 것 같으면 주석을 반드시 적어놓으세요.

## 리터럴 {#literal-constants}

`5`, `1.23`, `'This is a string'`, `"It's a string!"`처럼 절대 변하지 않는 데이터 그 자체를 리터럴 (literal)이라고 부릅니다.

리터럴([literal](https://dictionary.cambridge.org/dictionary/english/literal))은 영어로 **글자 그대로의**라는 뜻으로, _글자 그대로_ 값을 사용하기 때문에 붙은 이름입니다. 예를 들어, 숫자 `2`는 항상 2라는 값을 나타내고 절대로 변하지 않습니다.

> **참고: 다른 프로그래밍 언어에서 배우는 상수 (constant)와 리터럴의 차이점은 다음과 같습니다.**
> - 상수는 정의한 다음에 그 값을 지정해주어야 합니다.
> - 리터럴은 변수나 상수에 지정되거나 단독으로 쓰이는 값 그 자체를 말합니다.

## 숫자 (Numbers)

파이썬에서 숫자는 `2` 같은 정수형와 `3.23`나 `52.3E-4`같은 실수형으로 나눌 수 있습니다.

실수형 변수에서 `E`는 10의 제곱을 뜻합니다. 예를 들면, `52.3E-4`는 `52.3 * 10^-4^`와 같은 뜻입니다.

> **숙련된 프로그래머라면 참고하세요**
> 
> 파이썬 3에서 `long` 자료형은 존재하지 않으며, `int` 자료형에 모든 크기의 정수를 저장할 수 있습니다.

## 문자열 {#strings}

문자열은 단어나 문장처럼 여러 개의 문자가 모인 것을 말합니다.

문자열은 파이썬 프로그래머라면 반드시 알아두어야 하는 부분이므로, 아래의 내용을 잘 기억해두도록 합시다.

### 따옴표

문자열은 `'Quote me on this'`이나 `"What's your name?"`처럼 작은 따옴표나 큰 따옴표 안에 저장합니다. 따옴표 안에 있는 스페이스나 탭 등의 공백은 그대로 저장됩니다.

여러 줄의 문자열은 `"""`이나 `'''` 안에 저장합니다. `"""`이나 `'''` 안에서는 다음과 같이 작은 따옴표나 큰 따옴표를 자유롭게 사용할 수 있습니다.

```python
'''This is a multi-line string. This is the first line.
This is the second line.
"What's your name?," I asked.
He said "Bond, James Bond."
'''
```

### 문자열의 특성

문자열은 한번 만들면 그 내용을 절대로 다시 변경할 수 없습니다. 처음에는 익숙하게 느껴지지 않을 수도 있겠지만, 
이 책을 읽다 보면 이러한 문자열의 특성이 큰 문제가 되지 않는다는 것을 깨닫게 될 것입니다.

> **C/C++ 프로그래머라면 참고하세요**
> 
> 파이썬에는 `char` 같이 문자를 따로 저장할 수 있는 자료형이 없습니다.

<!-- -->

> **Perl/PHP 프로그래머라면 참고하세요**
> 
> 파이썬에서는 문자열을 작은 따옴표로 둘러싸든 큰 따옴표로 둘러싸든 차이가 없다는 사실!

### `format` 메소드 사용하기

문자열에 수식이나 변수의 값 같은 여러가지 정보를 넣어야 할 때는 `format` 메소드를 사용합니다.

아래의 코드를 `str_format.py`로 저장하고 실행하세요:

```python
age = 20
name = 'Swaroop'

print('{0} was {1} years old when he wrote this book'.format(name, age))
print('Why is {0} playing with that python?'.format(name))
```

실행 결과:

```
$ python str_format.py
Swaroop was 20 years old when he wrote this book
Why is Swaroop playing with that python?
```

**코드 설명**

문자열을 만들 때는 데이터를 어느 위치에 출력해야 하는지를 지정할 수 있으며, `format` 메소드에 넘겨준 값을 통해 그 자리에 어떤 정보가 들어가야 하는지를 지정할 수 있습니다.

위 코드에서 첫 번째 형식 지정자인 `{0}`는 `format` 메소드의 첫 번째 인수인 변수 `name`에 대응하고, 두 번째 형식 지정자인 `{1}`은 `format` 메소드의 두 번째 인수인 변수 `age`에 대응하는 것을 확인할 수 있습니다.
또한 여기서 형식 지정자의 인덱스는 0부터 시작한다는 사실을 알 수 있습니다.

```python
name + ' is ' + str(age) + ' years old'
```

물론, 위의 코드처럼 문자열 여러 개를 이어 붙이는 것도 가능하지만, 깔끔해보이지 않고 오류가 발생할 가능성이 높다는 것을 확인할 수 있습니다.
`format` 메소드을 사용해서 얻을 수 있는 또다른 장점은 숫자 등을 문자열로 직접 변환할 필요 없이 자동으로 변수의 값을 문자열로 변환할 수 있다는 것입니다.
또한, 문자열에 사용되는 변수의 이름이 바뀌더라도 문자열을 직접 바꾸지 않아도 된다는 장점이 있습니다.

`format` 메소드에서 형식 지정자의 인덱스는 생략이 가능하기 때문에, 다음과 같이 코드를 작성해도 무방합니다.

```python
age = 20
name = 'Swaroop'

print('{} was {} years old when he wrote this book'.format(name, age))
print('Why is {} playing with that python?'.format(name))
```

다음과 같이 인수를 직접 지정할 수도 있습니다.

```python
age = 20
name = 'Swaroop'

print('{name} was {age} years old when he wrote this book'.format(name=name, age=age))
print('Why is {name} playing with that python?'.format(name=name))
```

파이썬 3.6에서는 `format` 메소드를 사용하지 않아도 자동으로 형식을 만들어주는 **f-문자열** 기능이 추가되었습니다.

```python
age = 20
name = 'Swaroop'

print(f'{name} was {age} years old when he wrote this book')  # notice the 'f' before the string
print(f'Why is {name} playing with that python?')  # notice the 'f' before the string
```

아래와 같이 형식 지정자의 출력 형식을 세부적으로 지정할 수도 있습니다.

```python
# decimal (.) precision of 3 for float '0.333'
print('{0:.3f}'.format(1.0/3))
# fill with underscores (_) with the text centered
# (^) to 11 width '___hello___'
print('{0:_^11}'.format('hello'))
# keyword-based 'Swaroop wrote A Byte of Python'
print('{name} wrote {book}'.format(name='Swaroop', book='A Byte of Python'))
```

실행 결과:

```
0.333
___hello___
Swaroop wrote A Byte of Python
```

### `print` 함수

`print` 함수를 사용할 때는 문자열 끝에 줄넘김(`\n`)이 자동으로 추가된다는 것을 기억해야 합니다. 줄넘김을 원하지 않는다면 아래 코드와 같이 문자열 끝에 들어갈 문자를 직접 지정해 줄이 넘어가지 않도록 할 수 있습니다.

```python
print('a', end='')
print('b', end=' ')
print('c')
```

출력:

```
ab c
```

### 이스케이프 문자 {#escape-sequences}

만약 작은 따옴표(`'`)가 포함된 문구를 출력해야 한다고 생각해봅시다. 예를 들어 **'What's your name?'** 라는 문장이 있다고 하면 파이썬은 중간의 작은 따옴표가 문장의 끝이라고 생각해 오류를 표시합니다. 이런 오류를 피하기 위해서 우리는 *이스케이프 문자*를 사용해야 합니다. 파이썬은 이스케이프 문자로 백슬래시(`\`)를 사용하며 위의 경우 **'What\'s your name?'** 로 표기할 수 있습니다.

이스케이프 문자를 사용하지 않는 다른 방법으로 쌍 따옴표(`"`)를 사용할 수도 있습니다. **"What's your name?"** 이렇게 표현하면 파이썬이 문장의 끝이 어디인지 알 수 있습니다. 또한 백슬래시를 출력해야 하면 `\\`처럼 표현해야 파이썬에서 오류가 발생하지 않습니다.

문장이 두 줄로 출력되게 하려면 어떻게 해야 할까요? 하나의 방법은 이미 앞에서 배운 [따옴표 3개](#triple-quotes)를 사용하는 것입니다. 또다른 방법으로는 문장에 줄넘김 문자(`\n`)를 넣는 것입니다.

예를 들면 이렇게 말이죠.

```python
'This is the first line\nThis is the second line'
```

또 다른 유용한 이스케이프 문자에는 들여쓰기(tab; `\t`)가 있습니다. 이외에도 다양한 이스케이프 문자들이 있지만 여기에서는 가장 많이 사용되는 것만 알아보았습니다.

문자열 출력에서 또 하나 알아두어야 할 것은 하나의 백슬래쉬(`\`)를 사용해 긴 문자열을 짧게 표현 할 수 있다는 것입니다. 예를 들어 다음의 코드는

```python
"This is the first sentence. \
This is the second sentence."
```

아래의 코드와 동일합니다.

```python
"This is the first sentence. This is the second sentence."
```

### 순수 문자열 {#raw-string}

프로그램을 작성하다 보면 문자열 안의 이스케이프 문자를 처리하지 않고 그대로 사용하고 싶을 때가 있는데, 이럴 때 필요한 것이 바로 문자열 앞에 `r` 또는 `R`이 붙은 순수 문자열 (raw string)입니다.

```python
r"Newlines are indicated by \n"
```

> **정규 표현식을 사용하기 전 꼭! 확인하세요!**
> 
> 정규 표현식을 다룰 때에는 반드시 순수 문자열을 사용하세요. 순수 문자열을 사용하지 않을 경우 필요한 곳에 백슬래시를 일일이 넣어주어야 할 수도 있습니다. 예를 들어, 정규 표현식의 역참조는 `'\\1'` 또는 `r'\1'`와 같이 나타낼 수 있습니다.

## 변수 {#variable}

프로그램을 작성할 때는 리터럴 상수 대신에 어떤 값을 저장도 할 수 있고 변경도 할 수 있는 무언가가 필요할 때가 있는데, 이것을 _변수_ (variable)라고 합니다. 변수는 이름에서 알 수 있듯이 그 값이 변할 수 있으며, 변수에는 어떤 값이든 저장할 수 있습니다. 사실 변수는 여러가지 정보가 저장되는 컴퓨터의 메모리 공간의 일부인데, 리터럴 상수와 다른 점은 변수에 접근할 때에는 그 변수에 붙은 고유한 이름을 사용한다는 것입니다.

## 식별자 규칙 {#identifier-naming}

Variables are examples of identifiers. _Identifiers_ are names given to identify _something_. There are some rules you have to follow for naming identifiers:

- The first character of the identifier must be a letter of the alphabet (uppercase ASCII or lowercase ASCII or Unicode character) or an underscore (`_`).
- The rest of the identifier name can consist of letters (uppercase ASCII or lowercase ASCII or Unicode character), underscores (`_`) or digits (0-9).
- Identifier names are case-sensitive. For example, `myname` and `myName` are _not_ the same. Note the lowercase `n` in the former and the uppercase `N` in the latter.
- Examples of _valid_ identifier names are `i`, `name_2_3`. Examples of _invalid_ identifier names are `2things`, `this is spaced out`, `my-name` and `>a1b2_c3`.

## 자료형 {#data-types}

변수는 여러 종류의 값을 가질 수 있는데, 이러한 값의 종류를 _자료형_ (data types)이라고 합니다. 위에서 배운 숫자와 문자열은 파이썬의 기본 자료형에 해당됩니다. 또한 [클래스](./oop.md#class)라는 개념을 사용하면 새로운 자료형을 만들 수도 있는데, 이에 관한 내용은 나중에 다루도록 하겠습니다.

## 객체 {#object}

Remember, Python refers to anything used in a program as an _object_.  This is meant in the generic sense. Instead of saying "the _something_"', we say "the _object_".

> **Note for Object Oriented Programming users**:
>
> Python is strongly object-oriented in the sense that everything is an object including numbers, strings and functions.

We will now see how to use variables along with literal constants. Save the following example and run the program.

## 기본적인 파이썬 프로그램 작성법

Henceforth, the standard procedure to save and run a Python program is as follows:

### For PyCharm

1. Open [PyCharm](./first_steps.md#pycharm).
2. Create new file with the filename mentioned.
3. Type the program code given in the example.
4. Right-click and run the current file.

NOTE: Whenever you have to provide [command line arguments](./modules.md#modules), click on `Run` -> `Edit Configurations` and type the arguments in the `Script parameters:` section and click the `OK` button:

![PyCharm command line arguments](./img/pycharm_command_line_arguments.png)

### For other editors

1. Open your editor of choice.
2. Type the program code given in the example.
3. Save it as a file with the filename mentioned.
4. Run the interpreter with the command `python program.py` to run the program.

### Example: Using Variables And Literal Constants

Type and run the following program:

```python
# Filename : var.py
i = 5
print(i)
i = i + 1
print(i)

s = '''This is a multi-line string.
This is the second line.'''
print(s)
```

Output:

```
5
6
This is a multi-line string.
This is the second line.
```

**How It Works**

Here's how this program works. First, we assign the literal constant value `5` to the variable `i` using the assignment operator (`=`). This line is called a statement because it states that something should be done and in this case, we connect the variable name `i` to the value `5`. Next, we print the value of `i` using the `print` statement which, unsurprisingly, just prints the value of the variable to the screen.

Then we add `1` to the value stored in `i` and store it back. We then print it and expectedly, we get the value `6`.

Similarly, we assign the literal string to the variable `s` and then print it.

> **Note for static language programmers**
> 
> Variables are used by just assigning them a value. No declaration or data type definition is needed/used.

## 논리적 줄과 물리적 줄 {#logical-and-physical-line}

물리적 줄이란 프로그램을 짤 때 보이는 _말 그대로의 줄_을 의미하고, 논리적 줄이란 _파이썬 인터프리터가_ 처리하는 하나의 문장을 의미합니다. 
파이썬은 각각의 _물리적 줄_이 _논리적 줄_과 같다는 가정, 즉 사람 눈에 보이는 한 줄이 파이썬에서의 한 문장과 같다는 가정 하에 프로그램을 처리합니다.

논리적 줄의 예시로는 `print('hello world')`를 들 수 있는데, 만약 이 문장이 텍스트 편집기에서 한 줄에 있었다면 이 논리적 줄은 하나의 물리적 줄과 대응한다고 할 수 있습니다.

파이썬은 암묵적으로 한 줄에 단 하나의 문장만 사용해서 코드의 가독성을 높이는 것을 권장하고 있습니다. 하나의 물리적 줄에 여러 개의 논리적 줄을 넣고 싶을 때는 논리적 줄의 끝을 의미하는 세미콜론 (`;`)을 사용합니다.

```python
i = 5
print(i)
```

is effectively same as

```python
i = 5;
print(i);
```

which is also same as

```python
i = 5; print(i);
```

and same as

```python
i = 5; print(i)
```

However, I *strongly recommend* that you stick to *writing a maximum of a single logical line on each single physical line*. The idea is that you should never use the semicolon. In fact, I have _never_ used or even seen a semicolon in a Python program.

There is one kind of situation where this concept is really useful: if you have a long line of code, you can break it into multiple physical lines by using the backslash. This is referred to as _explicit line joining_:

```python
s = 'This is a string. \
This continues the string.'
print(s)
```

Output:

```
This is a string. This continues the string.
```

Similarly,

```python
i = \
5
```

is the same as

```python
i = 5
```

Sometimes, there is an implicit assumption where you don't need to use a backslash. This is the case where the logical line has a starting parentheses, starting square brackets or a starting curly braces but not an ending one. This is called *implicit line joining*. You can see this in action when we write programs using [list](./data_structures.md#lists) in later chapters.

## 들여쓰기 {#indentation}

파이썬에서 공백은 매우 중요한데, *줄 바로 앞에 있는 공백*은 특히 더 중요합니다. 각각의 줄 앞에 적절한 수의 공백을 넣는 작업을 _들여쓰기_라고 하는데, 논리적 줄의 맨 앞의 공백 (스페이스와 탭)은 그 줄의 들여쓰기 단계를 결정하는 데에 사용되고 어느 기능을 구성하는 문장인지도 결정합니다.

이것은 하나의 기능을 구성하는 모든 문장을 똑같이 들여써야 함을 의미하는데, 이렇게 기능 하나를 이루는 여러 문장의 묶음을 블록 (block)이라고 합니다. 이 책을 계속 읽다 보면 블록이 얼마나 중요한지를 알게 될 것입니다.

코드를 작성할 때 들여쓰기를 제대로 하지 않으면 어떻게 되는지 예제를 통해 직접 확인해봅시다.

```python
i = 5
# Error below! Notice a single space at the start of the line
 print('Value is', i)
print('I repeat, the value is', i)
```

프로그램을 실행하면 다음과 같은 오류가 발생하는 것을 확인할 수 있습니다.

```
  File "whitespace.py", line 3
    print('Value is', i)
    ^
IndentationError: unexpected indent
```

Notice that there is a single space at the beginning of the second line. The error indicated by Python tells us that the syntax of the program is invalid i.e. the program was not properly written. What this means to you is that _you cannot arbitrarily start new blocks of statements_ (except for the default main block which you have been using all along, of course). Cases where you can use new blocks will be detailed in later chapters such as the [control flow](./control_flow.md#control_flow).

> **들여쓰기 팁**
> 
> 파이썬은 들여쓰기로 공백 4개를 사용하는 것을 권장하고 있습니다. 대부분의 파이썬 IDE는 공백 4개를 자동으로 넣어줄 것입니다. 
들여쓰기를 할 때 공백을 일정한 개수로 넣지 않으면 프로그램이 제대로 실행되지 않을 수 있습니다.

<!-- -->

> **중괄호에 익숙한 프로그래머라면 주의하세요**
> 
> 파이썬에서 블록을 만들기 위해서는 중괄호 대신 무조건 공백을 사용해야 합니다.

## 정리

이번 장에서는 파이썬 프로그래머가 되기 위해 꼭 필요한 기초 지식에 대해 배웠습니다. 반드시 모든 내용을 완벽하게 이해하고 다음 장으로 넘어가도록 합시다.

