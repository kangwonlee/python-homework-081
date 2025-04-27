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

* Take an `int` `n` from input function : maximum order of the polynomial.
* Print a string of `'=========='`.
* Print `n` using the following f string:
  ``` python
  f'n = {n:1d}'
  ```
* If `n` is smaller than 2 or larger than 5, print following error message and do not process further. Use `if` `elif` `else` block for input validation.
  ``` python
  'Error : invalid n (2 <= n <= 5)'
  ```
* take `n+1` `int` coefficients from input and store in a `list`. Order would be higher to lower. For example:
  $$
  a_0 x^n + a_1 x^{n-1} + a_2 x^{n-2} + \cdots + a_{n-1}x + a_n
  $$
  will be stored as:
  ``` python
  [a_0, a_1, a_2, ... a_n_1, a_n]
  ```
* Print a string of `'=========='`.
* Print the number of coefficient `n_coef` using the following f string:
  ``` python
  f'n_coef = {n_coef:1d}'
  ```
* Print the highest order coefficient ($a_0$) using the following f string:
  ``` python
  f'a_0 = {a_0:8d}'
  ```
* If the highest order coefficient ($a_0$) is zero, print the following error message and do not process further.
  ``` python
  'Error : a_0 is zero'
  ```
* take an `int` `x` from input
* Print a string of `'=========='`.
* print the `list` containing polynomial coefficiets
* print `x` 
* print the evaluation result of the polynomial at `x`.

## Example Run 실행 예시:

### `n` == 2
```
n = 2
==========
a_0 = 1
a_1 = -6
a_2 = 9
==========
coefs : [1, -6, 9]
x = 3
result = 0
```

### `n` == 4
```
n = 4
==========
a_0 = 1
a_1 = 0
a_2 = 2
a_3 = 0
a_4 = 4
==========
coefs : [1, 0, 2, 0, 4]
x = 2
result = 28
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
