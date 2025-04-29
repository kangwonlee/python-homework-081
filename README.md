# Polynomial Evaluation 다항식 계산

* Please work on `exercise.py`.<br>`exercise.py` 파일을 수정하여 제출하세요.

## Purpose 목적:

* Using the user input, let's implement a program that will evalute a polynomial.<br>사용자 입력을 받아 들여 다항식을 계산하는 프로그램을 만들어 봅시다.
* Let's try to mimic how some of the widely used numerical software such as MATLAB and Python's NumPy evaluate a polynomial.<br>널리 사용되는 연산 소프트웨어인 MATLAB 이나 Python의 NumPy 가 다항식을 계산하는 방식을 흉내내봅시다.

## Steps 단계:

* Get `n` and validate<br>`n`을 입력받고 검증
* Collect coefficients in a list<br>매개변수를 입력 받아 `list` 에 저장
* Check if the highest order coefficient is zero<br>가장 높은 차수의 계수가 0인지 확인
* Get `x` from input<br>`x`를 입력받음
* Evaluate the polynomial<br>다항식을 계산

## Instructions 지침:

* Take an `int` `n` from input function using the following prompt :<br>`int` 값을 받아 변수 `n`에 저장하시오. 사용 프롬프트 :
  ``` python
  'maximum order of the polynomial in [2, 5] n = '
  ```
* Print a string 문자열 출력 : `'=========='`
* Print `n` using the following f string :<br>`n`을 표시하시오. 사용 f 문자열 :
  ``` python
  f'n\t{n:8d}'
  ```
* If `n` is smaller than 2 or larger than 5, print following error message and do not process further. Use `if` block for input validation.<br>`n`이 2보다 작거나 5보다 크면 다음 오류 메시지를 표시하고 이후의 처리는 하지 마시오. `if` 로 해당 입력 검증 로직을 구현하시오.
  ``` python
  'Error : invalid n (2 <= n <= 5)'
  ```
* Take `n+1` `int` coefficients from input and store in a `list`. Order would be higher to lower. For example:<br>`n+1`개의 `int` 계수를 입력으로부터 받아 `list` 로 저장하시오. 높은 차수 부터 낮은 차수의 순서로 저장하시오. 예를 들어 :
  $a_0 x^n + a_1 x^{n-1} + a_2 x^{n-2} + \cdots + a_{n-1}x + a_n$<br>
  will be stored as :<br>는 다음과 같이 저장될 것임 :
  ``` python
  [a_0, a_1, a_2, ... a_n_1, a_n]
  ```
  Please use the following prompt :<br>사용 프롬프트 :
  ``` python
  f'coefficient a_{i} = '
  ```
* Print a string 문자열 출력 : `'=========='`
* Print the number of coefficient `n_coef` using the following f string :<br>화면에 계수의 갯수 `n_coef` 를 표시하시오. 사용 프롬프트 :
  ``` python
  f'n_coef\t{n_coef:8d}'
  ```
* Print the highest order coefficient ($a_0$) using the following f string :<br>화면에 가장 높은 차수의 계수 ($a_0$)를 표시하시오. 사용 f문자열 :
  ``` python
  f'a_0\t{a_0:8d}'
  ```
* If the highest order coefficient ($a_0$) is zero, print the following error message and do not process further.<br>가장 높은 차수의 계수 ($a_0$) 가 0이면 다음 오류메시지를 표사하고 이후의 처리는 하지 마시오.
  ``` python
  'Error : a_0 is zero'
  ```
* Take an `int` `x` from input using the following prompt :<br>`int` 형 변수 `x` 를 입력 받으시오. 사용 프롬프트 :
  ``` python
  'x = '
  ```
* Print a string 문자열 출력 : `'=========='`
* Print the `list` containing polynomial coefficients using prefix :<br>화면에 다항식의 계수를 담은 `list`를 표시하시오. 사용 안내 문자열 :
  ``` python
  'coefs :'
  ```
* Print `x` using the following f string:<br>`x`를 표시하시오. 사용 프롬프트 :
  ``` python
  f'x\t{x:8d}'
  ```
* Print the evaluation result of the polynomial at `x` using the following prompt :<br>`x`에서의 다항식 연산 결과를 표시하시오. 사용 프롬프트 :
  ``` python
  f'result\t{result:8d}'
  ```

* Do not use 다음 키워드는 사용 않기 바람 : 'while', 'try', 'except', 'def', 'return', and 'lambda'.
* Please consider using these functions 다음 함수 사용을 생각해 보기 바랍니다 : 'print', 'input', 'int', 'range', 'len', and 'enumerate'

## Example Run 실행 예시:

### `n` == 2
```
maximum order of the polynomial in [2, 5] n = 2
==========
n	       2
coefficient a_0 = 1
coefficient a_1 = -6
coefficient a_2 = 9
==========
n_coef	       3
a_0	       1
x = 3
==========
coefs : [1, -6, 9]
x	       3
result	       0
```

### `n` == 4
```
maximum order of the polynomial in [2, 5] n = 4
==========
n	       4
a a_0 = 1
coefficient a_1 = 0
coefficient a_2 = 2
coefficient a_3 = 0
coefficient a_4 = 4
==========
n_coef	       5
a_0	       1
x = 2
==========
coefs : [1, 0, 2, 0, 4]
x	       2
result	      28
```

## Tips 팁:

* Test your program with a small polynomial, like `n=2` and coefficients `[1, 0, 1]` (i.e., $x^2 +1$), to ensure your evaluation is correct before trying larger polynomials.<br>프로그램 확인을 위해 작은 다항식을 활용하세요. 예를 들어 `n=2` 계수 `[1, 0, 1]` (즉, $x^2 +1$) 로 계산이 올바른지 확인한 후 더 큰 다항식을 시도하세요.
* Assume that the input is valid. If invalid, `int()` would raise an error and quit.<br>입력은 유효하다고 가정. 입력이 유효하지 않은 경우 `int()`가 오류를 발생시키고 중단시킬 것임.

__Happy coding!__

## Grading Criteria 채점 기준

| Criteria | Points |
|:--------:|:------:|
| Is the code written according to Python syntax?<br>코드가 파이썬 문법에 따라 작성되었는가? | 2 |
| Does the code satisfy the requirements?<br>코드가 요구사항을 충족하는가? | 3 |

``From here is common to all assignments.``

## Submission 제출 방법

1. Modify the contents of the `exercise.py` file to write your program.<br>`exercise.py` 파일의 내용을 수정하여 프로그램을 작성합니다.
2. Use the GitHub online editor to commit and push your changes. (See below for detailed instructions)<br>GitHub 온라인 편집기를 사용하여 수정 사항을 커밋하고 푸시합니다. (자세한 사용법은 아래 참조)
3. At the Actions tab of your Github repository, please check the result.<br>깃헙 저장소의 Actions 탭에서 결과를 확인 바랍니다.

## How to Use the GitHub Online Editor<br>Github 온라인 편집기 사용법

* Press the <kbd>.</kbd> key while viewing the files in your repository on GitHub. This will launch a web version of VS Code.<br>저장소의 [Code] 탭을 선택 후 <kbd>.</kbd> 키를 누르면 MS VS Code 의 Web version 이 시작됨
* Make your changes to the `exercise.py` file.<br>`exercise.py` 파일을 수정
* To commit your changes, click on the branch icon on the left sidebar (the third icon after the magnifying glass).<br>수정 사항을 commit 등록 하려면 왼쪽에서 줄 셋 아래 (확대경 다음) 세번째 가지치기 아이콘 선택
* Click the "+" sign next to the filename to stage your changes.<br>파일 이름의 오른쪽 + 기호 선택 (staging)
* Write a brief description of your changes in the text box above.<br>위 빈칸에 변경 사항 설명 입력
* Click "Commit & Push."<br>[커밋 및 푸시] 선택
* Click "Back to Repository" on the branch icon to return to your repository.<br>줄 셋 의 [리포지토리로 이동] 선택하여 저장소로 복귀

## NOTICE REGARDING STUDENT SUBMISSIONS<br>제출 결과물에 대한 알림

* Your submissions for this assignment may be used for various educational purposes. These purposes may include developing and improving educational tools, research, creating test cases, and training datasets.<br>제출 결과물은 다양한 교육 목적으로 사용될 수 있을 밝혀둡니다. (교육 도구 개발 및 개선, 연구, 테스트 케이스 및 교육용 데이터셋 생성 등).

* The submissions will be anonymized and used solely for educational or research purposes. No personally identifiable information will be shared.<br>제출된 결과물은 익명화되어 교육 및 연구 목적으로만 사용되며, 개인 식별 정보는 공유되지 않을 것입니다.

* If you do not wish to have your submission used for any of these purposes, please inform the instructor before the assignment deadline.<br>위와 같은 목적으로 사용되기 원하지 않는 경우, 과제 마감일 전에 강사에게 알려주기 바랍니다.

``Until here is common to all assignments.``
