## Chapter 6

```sh
파이썬에 대해 설명해줘.

너는 전문 프로그래밍 강사야.
초등학생이 이해할 수 있도록, 프로그래밍 언어 파이썬에서 ' 변수'의 정의와 사용 목적을 실생활 예시를 들어 설명해줘.
```

```sh
신제품 출시 안내 이메일 제목을 몇 개 추천해줘

신제품 출시 안내 이메일 제목을 몇 개 추천해줘
다음은 고객에게 발송하는 이메일 제목의 적절한 예시야.
이와 유사한 톤앤매너로 신제품 'Gemini Pro' 출시를 알리는 이메일 제목 5가지를 추천해줘.
예시 1: [신규 기능] 이제 더 스마트하게 작업하세요.
예시 2: 놓치지 마세요! 생산성을 향상시킬 새로운 업데이트 소식

```

```sh
다음 기사 내용을 세 개의 핵심 문장으로 요약해줘

[기사 전문] "인공지능(AI) 기술이 빠르게 발전하면서 우리 삶의 많은 부분이 변화하고 있습니다. 특히 자연어 처리 기술의 발전은 인간과 컴퓨터의 소통 방식을 혁신적으로 바꾸고 있으며, 이는 교육, 의료, 고객 서비스 등 다양한 분야에 적용되어 효율성을 높이고 있습니다.

…생략…

```

```sh
주요 프로그래밍 언어 3개를 제시해줘.

주요 프로그래밍 언어 3개를 JSON 형식으로 제시해줘.
```

```sh
Google의 AI 모델 '제미나이(Gemini)'에 대해 설명해줘.

Google의 AI 모델 '제미나이(Gemini)'에 대해 설명해줘.
기술적인 내용은 제외하고, 일반인이 이해하기 쉽게 200자 이내로 작성해줘. 역사나 개발 과정은 포함하지 마.
```

## Chapter 7

```markdown
# Project: My Awesome TypeScript Library

## General Instructions:

- TypeScript 코드 작성 시 기존 코딩 스타일을 따를 것
- 모든 함수와 클래스에 JSDoc 주석 작성
- 가능하면 함수형 프로그래밍 패러다임 사용
- TypeScript 5.0과 Node.js 20+ 호환성 보장

## Coding Style:

- 들여쓰기는 2칸(space) 사용
- 인터페이스는 I로 시작 (예 : IUserService)
- 클래스의 private 멤버는 \_로 시작
- 항상 strict equality(===, !==) 사용

## Specific Component: src/api/client.ts

- 모든 API 요청을 담당
- 신규 API 함수 추가 시 robust한 에러 처리 및 로깅 필수
- GET 요청은 반드시 fetchWithRetry 유틸리티 사용

## Dependencies:

- 반드시 필요한 경우가 아니면 외부 라이브러리 도입 금지
- 새 의존성 추가 시 사유 명시
```

```markdown
# 마크다운 (Markdown) 문법 가이드

마크다운은 읽고 쓰기 쉬운 텍스트 기반의 마크업 언어입니다. 이 문서는 주요 마크다운 문법을 정리하고 예시를 보여줍니다.

---

## 1. 제목 (Headers)

`#`의 개수로 제목의 수준을 표현합니다. `#`과 제목 텍스트 사이에는 공백이 필요합니다.

# 제목 1 (H1)

## 제목 2 (H2)

### 제목 3 (H3)

#### 제목 4 (H4)

##### 제목 5 (H5)

###### 제목 6 (H6)

---

## 2. 텍스트 스타일 (Text Styles)

텍스트를 강조하거나 특정 스타일을 적용할 수 있습니다.

- **굵게(Bold)**: `**텍스트**` 또는 `__텍스트__`
- _기울임(Italic)_: `*텍스트*` 또는 `_텍스트_`
- ~~취소선(Strikethrough)~~: `~~텍스트~~`
- **_굵고 기울임_**: `***텍스트***`
- `인라인 코드`: \`code\`와 같이 백틱으로 텍스트를 감쌉니다.
```

```markdown
# H1 제목

## H2 제목

### H3 제목
```

```markdown
- 항목 1

- 항목 2

1. 첫 번째

2. 두 번째
```

````markdown
`npm install -g gemini`

```
npm install -g gemini
gemini -v
```
````

```markdown
[공식 문서](https://example.com)

![로고](logo.png)
```

```markdown
_기울임_

**굵게**

~~취소선~~
```

```markdown
<!-- 여기에 작업할 내용 TODO: 문단 추가 예정 -->
```

```sh
/init
```

> [GEMINI.md](GEMINI.md) 파일을 참고합니다.

```sh

이 가이드를 바탕으로 지금 프로젝트에 대한 컨텍스트를 작성해줘.

## Building and running

Before submitting any changes, it is crucial to validate them by running the full preflight check. This

command will build the repository, run all tests, check for type errors, and lint the code.

To run the full suite of checks, execute the following command:

...생략...

```

## Chapter 8

```sh
/about
```

```sh
제미나이에 대해 설명해줘

/chat save GEMINI
/chat list
/chat resume GEMINI
```

````


```sh
/memory add “한국어로 답변해줘”
cat ~/.gemini/GEMINI.md
````

## Chapter 9

```sh
@http://github.com/google-gemini/gemini-cli/blob/main/docs/cli/commands.md 내용을 정리해줘

web_fetch를 사용해 @http://github.com/google-gemini/gemini-cli/blob/main/docs/cli/commands.md 내용을 정리해줘

```

```sh
list_directory 도구를 사용해 현재 디렉터리에 어떤 파일들이 있는지 확인해 줘, .png와 .md 파일은 무시해
```

```sh
prompt.pdf에는 어떤 내용이 있지?
```

```sh
2개의 숫자를 입력받아 합을 구하는 파이썬 코드를 sum.py에 작성해줘
```

```sh
gemini -m "gemini-2.5-flash"
gemini -p "google_web_search('최신 AI 뉴스를 소개해줘')"

gemini --show_memory_usage

gemini -v
gemini --version

gemini -y
gemini --yolo

gemini -a
gemini --all_files

gemini --debug
```

## Chapter 10

```sh
brew install git
brew install gh

git --version

cd gemini_proj
git init

git status
```

```sh
git config --global user.name "계정 이름"
git config --global user.email "이메일"
git remote add origin https://github.com/startedourmission/gemini_proj.git
```

```sh
gh auth login
```

```sh
.gemini/를 .gitignore에 추가해줘
cat .gitignore

README를 작성하고 프로젝트를 push해.
```
