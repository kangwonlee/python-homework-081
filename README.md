# Python Homework Template
Please work on : `exercise.py`

## Purpose 목적:

Why do we want to do this assignment? What do we want to accomplish?

## Description 설명:

* Describe homework here

## Instructions 지침:

* How to do this homework
* `classroom.yml` file is at `.github/workflows/` folder. `.github` folder is hidden on the Linux operating system but will be visible on the Github repository.
* Please set `vars.PYTHON_GRADER_???` (replace `???` with assignment identifier) in the repository settings (Settings > Secrets and Variables > Actions > Variables) to your grader image (e.g., `ghcr.io/your-org/python-pytest-301:latest`).
* Set your AI feedback natural language in `classroom.yml`.

## Example Run 실행 예시:

* input
```
input example here
```
* output
```
----------
output example here
```

## Tips 팁:

* please add some more hints here

__Happy coding!__

## Grading Criteria 채점 기준

| Criteria | Points |
|:--------:|:------:|
| Is the code written according to Python syntax?<br>코드가 파이썬 문법에 따라 작성되었는가? | 2 |
| Does the code satisfy the requirements?<br>코드가 요구사항을 충족하는가? | 3 |

<details>
<summary><h2>Instructor Setup</h2></summary>

This template is designed for use with [GitHub Classroom](https://classroom.github.com/). Before distributing to students, configure the following in your GitHub organization or repository settings.

### How the Two-Repo Pattern Works

Each assignment requires **two** repositories:

1. **Homework template** (this repo) — student-facing, contains the assignment skeleton (`exercise.py`) and the `classroom.yml` workflow that pulls the grader image and runs tests on student pushes.
2. **Grader template** ([python-pytest-template](https://github.com/kangwonlee/python-pytest-template)) — instructor-facing, contains pytest test files and a Dockerfile. Its CI builds and publishes a grader Docker image to GHCR.

### Required Secrets

Set these in **Settings > Secrets and variables > Actions > Secrets** at the organization level (recommended) or per repository.

#### `CR_PAT` (required)

A GitHub Personal Access Token used to pull the grader Docker image from GHCR.

1. Go to **GitHub > Settings (user) > Developer settings > Personal access tokens > Fine-grained tokens**.
2. Click **Generate new token**.
3. Set the following permissions:

| Permission | Access | Purpose |
|:----------:|:------:|:--------|
| Packages   | Read   | Pull grader Docker images from GHCR |

4. Copy the token and save it as a repository or organization secret named `CR_PAT`.

> If using GitHub Classroom, set `CR_PAT` as an **organization secret** so all student repos inherit it automatically.

#### LLM API Keys (at least one required)

The AI tutor step provides personalized feedback to students. At least one key must be set. The workflow validates this and fails early if none are configured.

| Secret Name | Service | Where to Obtain |
|:-----------:|:-------:|:----------------|
| `CLAUDE_API_KEY` | Anthropic Claude | https://console.anthropic.com/ |
| `GOOGLE_API_KEY` | Google Gemini | https://aistudio.google.com/ |
| `XAI_API_KEY` | xAI Grok | https://console.x.ai/ |
| `NVIDIA_NIM_API_KEY` | NVIDIA NIM | https://build.nvidia.com/ |
| `PERPLEXITY_API_KEY` | Perplexity | https://perplexity.ai/settings/api |

#### `DEFAULT_MODEL` (optional)

Specifies the preferred LLM model. If unset, the AI tutor defaults to Gemini or uses whichever single key is available.

### Repository Variable

Set in **Settings > Secrets and variables > Actions > Variables** tab.

#### `PYTHON_GRADER_???`

Replace `???` with your assignment identifier (e.g., `PYTHON_GRADER_301` for assignment 301). The value is the full GHCR image URL of the grader, e.g.:

```
ghcr.io/your-org/python-pytest-301:latest
```

If this variable is not set, the workflow falls back to auto-constructing the URL as `ghcr.io/{owner}/python-pytest-{assignment_num}:latest`, where `{assignment_num}` is extracted from the repository name.

### Customizing for a New Assignment

1. Use this template to create a new repository (click **Use this template** on GitHub).
2. Edit `README.md` — fill in the Purpose, Description, Instructions, Example Run, and Tips sections.
3. Edit `exercise.py` — provide starter code or an empty skeleton for students.
4. Update the grading criteria table if point allocations differ.
5. Set `INPUT_EXPLANATION-IN` in `classroom.yml` to the desired feedback language (default: `"English"`).
6. Set the `CR_PAT` secret, at least one LLM API key, and the `PYTHON_GRADER_???` variable.

</details>

``From here is common to all assignments.``

## Submission 제출 방법

1. Modify the contents of the `exercise.py` file to write your program.<br>`exercise.py` 파일의 내용을 수정하여 프로그램을 작성합니다.
2. Use the GitHub online editor to commit and push your changes. (See below for detailed instructions)<br>GitHub 온라인 편집기를 사용하여 수정 사항을 커밋하고 푸시합니다. (자세한 사용법은 아래 참조)
3. At the Actions tab of your Github repository, please check the result.<br>깃헙 저장소의 Actions 탭에서 결과를 확인 바랍니다.

## Shared Computer Warning<br>공용 컴퓨터 사용 시 주의사항

* **University labs**: Always use **incognito/private mode** (<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>N</kbd>) to access GitHub. Closing the window automatically logs you out.<br>**대학 컴퓨터실**: 반드시 **시크릿 모드** (<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>N</kbd>)로 GitHub에 접속하세요. 창을 닫으면 자동으로 로그아웃됩니다.

<details>
<summary><h2>How to Use the GitHub Online Editor<br>Github 온라인 편집기 사용법</h2></summary>

* Press the <kbd>.</kbd> key while viewing the files in your repository on GitHub. This will launch a web version of VS Code.<br>저장소의 [Code] 탭을 선택 후 <kbd>.</kbd> 키를 누르면 MS VS Code 의 Web version 이 시작됨
* Make your changes to the `exercise.py` file.<br>`exercise.py` 파일을 수정
* To commit your changes, click on the branch icon on the left sidebar (the third icon after the magnifying glass).<br>수정 사항을 commit 등록 하려면 왼쪽에서 줄 셋 아래 (확대경 다음) 세번째 가지치기 아이콘 선택
* Click the "+" sign next to the filename to stage your changes.<br>파일 이름의 오른쪽 + 기호 선택 (staging)
* Write a brief description of your changes in the text box above.<br>위 빈칸에 변경 사항 설명 입력
* Click "Commit & Push."<br>[커밋 및 푸시] 선택
* Click "Back to Repository" on the branch icon to return to your repository.<br>줄 셋 의 [리포지토리로 이동] 선택하여 저장소로 복귀

</details>


<details>
<summary><h2>Common Git Commands<br>주요 Git 명령어</h2></summary>

If you work with Git from a terminal (e.g., VS Code terminal, WSL, or macOS Terminal), these are the commands you will use most often.<br>터미널(VS Code 터미널, WSL, macOS 터미널 등)에서 Git을 사용하는 경우, 가장 자주 사용하는 명령어입니다.

| Command | Description |
|:--------|:------------|
| `git status` | Show which files have been changed<br>변경된 파일 확인 |
| `git add <file>` | Stage a file for commit<br>커밋할 파일 준비 (스테이징) |
| `git commit -m "message"` | Save staged changes with a description<br>스테이징된 변경 사항을 메시지와 함께 저장 |
| `git push` | Send commits to GitHub<br>커밋을 GitHub에 전송 |
| `git log --oneline` | View commit history (one line per commit)<br>커밋 히스토리 조회 (한 줄씩) |
| `git diff` | See what changed before committing<br>커밋 전 변경 내용 확인 |

**Typical workflow**<br>**일반적인 작업 흐름:**

```bash
git add exercise.py
git commit -m "Add loop to calculate factorial"
git push
```

</details>

## Writing Descriptive Git Commit Messages<br>커밋 메시지 작성 권고안

* To help you develop better coding habits, we encourage descriptive Git commit messages when committing changes to your repository.<br>보다 바람직한 코딩 습관을 기르기 위해, 저장소에 변경 사항을 등록할 때 메시지에 보다 자세히 설명하는 것을 권합니다.
* A good commit message clearly explains what you changed and why, making it easier for you to understand your work later.<br>바람직한 커밋 메시지는 무엇을 변경했는지, 왜 변경했는지를 명확히 설명하여 나중에 수정 사항을 이해하기 쉽게 도와줄 것입니다.

### Guidelines for Commit Messages<br>메시지 작성 지침

* **Use the imperative mood** — write as if giving an instruction: "Add", "Fix", "Update", "Refactor".<br>**명령형으로 작성** — "Add", "Fix", "Update", "Refactor"와 같은 동사로 시작합니다.
* **Capitalize the first word** and do not end with a period.<br>**첫 글자는 대문자**로 쓰고, 마침표는 붙이지 않습니다.
* **Keep it concise** — aim for 15–50 characters, but ensure clarity.<br>**간결하게** — 15–50자 정도로 작성하되, 명확성을 유지합니다.
* **Be specific** — describe *what* changed and *why*, not just "update" or "fix".<br>**구체적으로** — 무엇을 왜 변경했는지 설명합니다. 단순히 "update"나 "fix"는 너무 일반적입니다.

### Examples 예시

| | Message | Why |
|:---:|:--------|:----|
| Good | `Add factorial function to exercise.py` | Clearly states what was added<br>무엇을 추가했는지 명확히 설명 |
| Good | `Fix off-by-one error in loop counter` | Identifies the bug and location<br>버그와 위치를 구체적으로 식별 |
| Good | `Update print format to match expected output` | Explains purpose of the change<br>변경의 목적을 설명 |
| Bad | `update` | Too vague — what was updated?<br>너무 모호 — 무엇을 수정했는지 알 수 없음 |
| Bad | `fix 1` | No context — fix what?<br>맥락 없음 — 무엇을 수정했는지 알 수 없음 |
| Bad | `changed file` | Every commit changes a file — this says nothing<br>모든 커밋은 파일을 변경함 — 아무 정보도 없음 |

### Why It Matters<br>왜 중요한가

* Clear commit messages improve collaboration, debugging, and code review in real-world projects.<br>커밋 메시지가 명확하면 프로젝트 실무에서 공동 작업, 버그 수정, 코드 검토에서 도움을 얻을 수 있을 것입니다.
* Your commit history tells the story of how your code evolved — make it readable.<br>커밋 히스토리는 코드가 어떻게 발전했는지 보여주는 기록입니다 — 읽기 쉽게 작성하세요.

### Resources 참고 자료
* [How to Write a Git Commit Message](https://cbea.ms/git-commit/)
* [좋은 Git Commit message 작성법](https://velog.io/@k-minsik/좋은-Git-Commit-message-작성법)

<details>
<summary><h2>NOTICE REGARDING STUDENT SUBMISSIONS<br>제출 결과물에 대한 알림</h2></summary>

* Your submissions for this assignment may be used for various educational purposes. These purposes may include developing and improving educational tools, research, creating test cases, and training datasets.<br>제출 결과물은 다양한 교육 목적으로 사용될 수 있을 밝혀둡니다. (교육 도구 개발 및 개선, 연구, 테스트 케이스 및 교육용 데이터셋 생성 등).

* The submissions will be anonymized and used solely for educational or research purposes. No personally identifiable information will be shared.<br>제출된 결과물은 익명화되어 교육 및 연구 목적으로만 사용되며, 개인 식별 정보는 공유되지 않을 것입니다.

* If you do not wish to have your submission used for any of these purposes, please inform the instructor before the assignment deadline.<br>위와 같은 목적으로 사용되기 원하지 않는 경우, 과제 마감일 전에 강사에게 알려주기 바랍니다.

</details>

## Acknowledgments

* The template for this assigment is registered as a part of #C-2025-016393 in the Korea Copyright Commission.
* Various LLMs and AI tools helped implement the templates for this assignment.<br>다양한 LLM 및 AI 도구가 이 과제의 템플릿 구현에 도움을 주었습니다.
    - Google Gemini
    - xAI Grok3
    - Claude.ai
    - Perplexity Sonar

``Until here is common to all assignments.``
