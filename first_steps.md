# 첫 번째 프로그램 만들기

이제 'hello world'라는 문자열을 화면에 표시하는 파이썬 프로그램을 만들어 보면서, 프로그램의 기본 작성 방법, 저장 방법과 실행 방법을 알아보겠습니다.

파이썬 프로그램은 파이썬 인터프리터로 실행하거나 소스 코드에서 바로 실행할 수 있습니다.

## 파이썬 인터프리터로 프로그램 실행하기

Windows에서는 `명령 프롬프트`, Mac OS X나 GNU/Linux에서는 `터미널` 또는 `gnome-terminal`을 실행한 다음, `python3`을 실행하고 `[enter]` 키를 누릅니다. (이전 장 `[파이썬 설치하기](./installation.md#installation) chapter)`를 참고하세요)

파이썬을 실행하면, 까만 창에 `>>>`가 보이고 `>>>` 뒤부터 입력을 할 수 있을 것입니다. 이것을 _파이썬 인터프리터_이라고 부릅니다.

이제 아래의 코드를 입력하고 `[enter]` 키를 눌러 봅시다.

```python
print("hello world")
```

`hello world`라는 글자가 화면에 표시되는 것을 확인할 수 있습니다.

Mac OS X에서는 실행 결과가 아래와 같이 보일 것입니다. 화면에 나오는 파이썬 버전은 설치된 파이썬 버전에 따라 아래와 다르게 보일 수도 있지만, `>>>` 뒤의 부분은 동일하게 표시될 것입니다.

<!-- The output should match pythonVersion variable in book.json -->
```python
$ python3
Python 3.6.0 (default, Jan 12 2017, 11:26:36)
[GCC 4.2.1 Compatible Apple LLVM 8.0.0 (clang-800.0.38)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> print("hello world")
hello world
```

Notice that Python gives you the output of the line immediately! What you just entered is a single Python _statement_. We use `print` to (unsurprisingly) print any value that you supply to it. Here, we are supplying the text `hello world` and this is promptly printed to the screen.

### 파이썬 인터프리터 종료하기

GNU/Linux나 OS X의 `터미널`을 사용하고 있다면, `[ctrl + d]` 키를 누르거나 `exit()`(`exit` 뒤의 `()`까지 빠짐없이 입력하세요)을 입력하고 `[enter]` 키를 눌러 파이썬 인터프리터를 종료할 수 있습니다.

Windows의 `명령 프롬프트`에서는 `[ctrl + z]` 키를 누른 다음, `[enter]` 키를 누르면 파이썬 인터프리터가 종료됩니다.

## 텍스트 편집기 또는 통합 개발 환경(IDE, Integrated Development Environment) 선택하기

We cannot type out our program at the interpreter prompt every time we want to run something, so we have to save them in files and can run our programs any number of times.

To create our Python source files, we need an editor software where you can type and save. A good programmer's editor will make your life easier in writing the source files. Hence, the choice of an editor is crucial indeed. You have to choose an editor as you would choose a car you would buy. A good editor will help you write Python programs easily, making your journey more comfortable and helps you reach your destination (achieve your goal) in a much faster and safer way.

One of the very basic requirements is _syntax highlighting_ where all the different parts of your Python program are colorized so that you can _see_ your program and visualize its running.

If you have no idea where to start, I would recommend using [PyCharm Educational Edition](https://www.jetbrains.com/pycharm-edu/) software which is available on Windows, Mac OS X and GNU/Linux. Details in the next section.

If you are using Windows, *do not use Notepad* - it is a bad choice because it does not do syntax highlighting and also importantly it does not support indentation of the text which is very important in our case as we will see later. Good editors will automatically do this.

If you are an experienced programmer, then you must be already using [Vim](http://www.vim.org) or [Emacs](http://www.gnu.org/software/emacs/). Needless to say, these are two of the most powerful editors and you will benefit from using them to write your Python programs. I personally use both for most of my programs, and have even written an [entire book on Vim]({{ book.vimBookUrl }}).

In case you are willing to take the time to learn Vim or Emacs, then I highly recommend that you do learn to use either of them as it will be very useful for you in the long run. However, as I mentioned before, beginners can start with PyCharm and focus the learning on Python rather than the editor at this moment.

To reiterate, please choose a proper editor - it can make writing Python programs more fun and easy.

## PyCharm으로 파이썬 프로그램 만들기 {#pycharm}

[PyCharm 커뮤니티 에디션](https://www.jetbrains.com/pycharm/download/#section=windows)은 파이썬 프로그램을 편리하게 작성할 수 있게 도와주는 IDE로, 간단한 사용법은 다음과 같습니다.

먼저, PyCharm을 실행하고, `Create New Project`를 클릭하세요.

![PyCharm에서 새 프로젝트 만들기](./img/pycharm_create_new_project.png)

여기서 `Pure Python`을 선택한 다음, `untitled`라고 되어있는 부분을 `helloworld`로 바꾸고 `Create` 버튼을 클릭하세요.

![PyCharm 프로젝트 이름 설정](./img/pycharm_create_new_project_pure_python.png)

이제 `helloworld` 폴더를 오른쪽 클릭한 다음, `New` -> `Python File`을 선택하세요.

![프로젝트에 새 파이썬 파일 추가하기](./img/pycharm_new_python_file.png)

새 파이썬 파일 이름을 지정하라는 창이 뜨면 `hello`를 입력하세요.

![PyCharm에서 파이썬 파일 이름 지정하기](./img/pycharm_new_file_input.png)

새 파이썬 파일이 만들어진 것을 확인할 수 있습니다.

![PyCharm hello.py file](./img/pycharm_hello_open.png)

이제 아래의 코드를 그대로 입력하세요.

<!-- TODO: Update screenshots for Python 3 -->

```python
print("hello world")
```
입력한 코드를 전체 선택한 다음, 오른쪽 클릭 메뉴에서 `Run 'hello'`를 클릭하세요.

![PyCharm Run 'hello'](./img/pycharm_run.png)

아래와 같이 프로그램이 `hello world`를 출력하는 것을 확인할 수 있습니다.

![PyCharm output](./img/pycharm_output.png)

Phew! That was quite a few steps to get started, but henceforth, every time we ask you to create a new file, remember to just right-click on `helloworld` on the left -> `New` -> `Python File` and continue the same steps to type and run as shown above.

You can find more information about PyCharm in the [PyCharm Quickstart](https://www.jetbrains.com/pycharm-educational/quickstart/) page.

## Vim 설치하기

1. 먼저 [Vim](http://www.vim.org)을 설치하세요.
    * Mac OS X를 사용하고 계시다면 [HomeBrew](http://brew.sh/)로 `macvim`을 설치해야 합니다.
    * Windows users should download the "self-installing executable" from [Vim website](http://www.vim.org/download.php)
    * GNU/Linux users should get Vim from their distribution's software repositories, e.g. Debian and Ubuntu users can install the `vim` package.
2. Install [jedi-vim](https://github.com/davidhalter/jedi-vim) plugin for autocompletion.
3. Install corresponding `jedi` python package : `pip install -U jedi`

## Emacs 설치하기

1. Install [Emacs 24+](http://www.gnu.org/software/emacs/).
    * Mac OS X users should get Emacs from http://emacsformacosx.com
    * Windows users should get Emacs from http://ftp.gnu.org/gnu/emacs/windows/
    * GNU/Linux users should get Emacs from their distribution's software repositories, e.g. Debian and Ubuntu users can install the `emacs24` package.
2. Install [ELPY](https://github.com/jorgenschaefer/elpy/wiki)

## 소스 코드로 프로그램 실행하기

Now let's get back to programming. There is a tradition that whenever you learn a new programming language, the first program that you write and run is the 'hello world' program - all it does is just say 'hello world' when you run it. As Simon Cozens[^1] says, it is the "traditional incantation to the programming gods to help you learn the language better."

Start your choice of editor, enter the following program and save it as `hello.py`.

If you are using PyCharm, we have already [discussed how to run from a source file](#pycharm).

For other editors, open a new file `hello.py` and type this:

```python
print("hello world")
```

Where should you save the file? To any folder for which you know the location of the folder. If you
don't understand what that means, create a new folder and use that location to save and run all
your Python programs:

- `/tmp/py` on Mac OS X
- `/tmp/py` on GNU/Linux
- `C:\py` on Windows

To create the above folder (for the operating system you are using), use the `mkdir` command in the terminal, for example, `mkdir /tmp/py`.

IMPORTANT: Always ensure that you give it the file extension of `.py`, for example, `foo.py`.

To run your Python program:

1. Open a terminal window (see the previous [Installation](./installation.md#installation) chapter on how to do that)
2. **C**hange **d**irectory to where you saved the file, for example, `cd /tmp/py`
3. Run the program by entering the command `python hello.py`. The output is as shown below.

```
$ python hello.py
hello world
```

![Screenshot of running program in terminal](./img/terminal_screenshot.png)

If you got the output as shown above, congratulations! - you have successfully run your first Python program. You have successfully crossed the hardest part of learning programming, which is, getting started with your first program!

In case you got an error, please type the above program _exactly_ as shown above and run the program again. Note that Python is case-sensitive i.e. `print` is not the same as `Print` - note the lowercase `p` in the former and the uppercase `P` in the latter. Also, ensure there are no spaces or tabs before the first character in each line - we will see [why this is important](./basics.md#indentation) later.

**How It Works**

A Python program is composed of _statements_. In our first program, we have only one statement. In this statement, we call the `print` _statement_ to which we supply the text "hello world".

## 도움말 보기

If you need quick information about any function or statement in Python, then you can use the built-in `help` functionality. This is very useful especially when using the interpreter prompt. For example, run `help('len')` - this displays the help for the `len` function which is used to count number of items.

TIP: Press `q` to exit the help.

Similarly, you can obtain information about almost anything in Python. Use `help()` to learn more about using `help` itself!

In case you need to get help for operators like `return`, then you need to put those inside quotes such as `help('return')` so that Python doesn't get confused on what we're trying to do.

## 정리

이번 장에서는 파이썬 프로그램의 기본 작성 방법, 저장 방법과 실행 방법을 알아보았습니다.

이제 파이썬의 기초를 쌓아보도록 하겠습니다.

---

[^1]: the author of the amazing 'Beginning Perl' book
