## Chapter 21

```sh
mkdir autoblog
cd autoblog
```

```sh
지금부터 자료 수집부터 블로그 글 작성, 게시까지 자동화하는 시스템을 만들거야. PRD를 작성해서 PRD.md로 저장해.

1. 키워드로 정보 수집

- 구글 검색을 사용해 최신 정보 수집 (search.md)
- Gemini image generation API를 사용해 블로그에 사용할 이미지 생성(image.jpg)

2. 수집한 내용을 바탕으로 블로그 포스트 초안 작성
- 블로그 포스트 초안 (draft.md)

3. quarto를 사용해 블로그 포스트 초안을 html로 변환 및 깃허브 페이지에 포스팅
- DIRECTORY/index.html
```

## Chapter 22

```json
{
  "name": "blog",
  "description": "A tool that writes a blog post using the specified text file and saves it as a markdown file.",
  "parameters": {
    "type": "object",
    "properties": {
      "filename": {
        "type": "string",
        "description": "The file path containing the material for the post."
      }
    },
    "required": ["filename"]
  }
}
```

```json
blog)
  read INPUT_JSON
  FILENAME=$(echo "$INPUT_JSON" | jq -r '.filename')
  # Check if the file exists
  if [[ ! -f "$FILENAME" ]]; then
    echo "{\"error\": \"File does not exist: $FILENAME\"}"
    exit 1
  fi

  # Create prompt for blog post draft
  PROMPT="@${FILENAME} 이 내용을 바탕으로 초보 개발자도 이해할 수 있게, 친절한 블로그 포스팅을 한국어로 작성해줘"

  # Run gemini CLI and capture stdout
  BLOG_POST=$(gemini -p "$PROMPT" -m "gemini-2.5-flash")

  # Add "draft-" prefix to filename
  BASENAME=$(basename "$FILENAME")
  MD_FILENAME="draft-${BASENAME%.*}.md"
  echo "$BLOG_POST" >"$MD_FILENAME"

  echo "{\"result\": \"Blog post has been saved as $MD_FILENAME!\"}"
  ;;
*)
```

```sh
blog FASTAPI.md
```

```markdown
GEMINI_API_KEY=<API_KEY>
```

```json
{
  "name": "gemini-image-gen",
  "description": "Generate an image using Gemini API from a text prompt.",
  "parameters": {
    "type": "object",
    "properties": {
      "prompt": {
        "type": "string",
        "description": "The prompt for image generation."
      }
    },
    "required": ["prompt"]
  }
}
```

```json
#!/bin/bash
if [ -f ".env" ]; then
    export $(grep -v '^#' .env | xargs)
fi
FUNC_NAME="$1"
shift
case "$FUNC_NAME" in
gemini-image-gen)
    read INPUT_JSON
    PROMPT=$(echo "$INPUT_JSON" | jq -r '.prompt')
    API_KEY="${GEMINI_API_KEY}"
    RESPONSE=$(curl -s -X POST \
"https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash-preview-image-generation:generateContent" \
        -H "x-goog-api-key: ${API_KEY}" \
        -H "Content-Type: application/json" \
        -d "{\"contents\":[{\"parts\":[{\"text\":\"${PROMPT}\"}]}], \
             \"generationConfig\":{\"responseModalities\":[\"TEXT\",\"IMAGE\"]}}"
    )
    IMAGE_DATA=$(echo "$RESPONSE" | grep -o '"data": "[^"]*"' | cut -d'"' -f4)
    OUT_FILE="gemini-image-$(date +%s).png"
    echo "$IMAGE_DATA" | base64 --decode > "$OUT_FILE"
    echo "{\"result\": \"Downloaded to $OUT_FILE\"}"
    ;;
*)
    echo "{\"error\": \"Unknown function: $FUNC_NAME\"}"
    exit 1
    ;;
esac
```

```markdown
## 이미지 생성

- gemini-image-gen 도구를 사용합니다.
- 예시: gemini-image-gen "A futuristic city skyline at sunset"
- 입력한 프롬프트에 따라 이미지를 생성합니다.
```

```sh
gemini gemini-image-gen을 사용해 'featured notebook' 이미지를 생성해줘
```

### Chapter 23

```sh
notebookLM의 Featured notebooks 기능'에 대해 검색해서 관련 자료를 3개 이상 정리해 줘
정리한 자료는 search.md에 작성하고 참고한 웹페이지의 위치도 포함시켜 줘
```

```sh
@search.md의 내용을 활용하여
NotebookLM에 새로 추가된 기능인 Featured Notebooks를 소개하는 블로그 아티클을 draft.md로 작성해 줘.
글의 구조는 다음을 참고하고, 전문적이지만 이해하기 쉬운 톤을 유지해 줘.
1. 도입: 독자들의 흥미를 끄는 질문으로 시작
2. 핵심 요약: 가장 중요한 내용 3가지를 요약 및 설명
3. 상세 설명: 각 내용에 대해 구체적인 예시와 함께 상세히 설명
4. 마무리: 이 내용의 의미와 앞으로 미칠 영향에 대한 전망으로 마무리
```

```sh
@draft.md의 내용을 참고하여 각 문단마다 설명 보충과 이해를 돕기 위한 이미지를 생성해 줘
```

```sh
생성한 이미지를 @draft.md의 본문에 추가하여 post.qmd 파일에 작성해줘
아티클의 맨 처음에는 @gemini-image-1753072196.png 이미지를 사용해
```

```sh
quarto render .
```

### Chapter 24

```sh
git clone https://github.com/jhk0530/Blog_AI.git
```

```sh
quarto create project blog
```

```sh
quarto preview .
```

```yml
project:
  type: website
  output-dir: docs
```

```sh
touch .nojekyll
```

```sh
quarto publish
```

```markdown
## 블로그 생성

- 블로그 생성은 다음의 단계를 거칩니다.

1. post 디렉터리에 키워드에 기반한 하나의 단어를 이름으로 사용하여 새로운 디렉터리를 생성합니다. 이후 생성하는 파일은 이 디렉터리에 저장합니다.
   - 예시: post/sunset
   - 이 디렉터리의 이름은 키워드로 사용됩니다.
2. 키워드를 기반으로 GoogleSearch 도구를 사용하여 최신 정보를 정리하여 search.md에 작성합니다.
   - 관련 자료는 3개 이상 정리하고, 참고한 웹페이지의 위치도 search.md에 포함하도록 합니다.
3. gemini-image-gen 도구를 사용하여 키워드를 설명하는 블로그 포스팅에 적합한 썸네일 이미지를 생성합니다.
   - 예시: gemini-image-gen "sunset"
   - 생성된 이미지는 post/sunset/ 디렉터리에 thumbnail.jpg라는 이름으로 저장합니다.
4. search.md의 내용을 바탕으로 블로그 포스트 초안을 작성한 뒤 draft.md에 작성합니다.
   - 글의 구조는 다음과 같습니다.
     1. 도입: 독자들의 흥미를 끄는 질문으로 시작
     2. 핵심 요약: 가장 중요한 내용 3가지를 요약 및 설명
     3. 상세 설명: 각 내용에 대해 구체적인 예시와 함께 상세히 설명
     4. 마무리: 이 내용의 의미와 앞으로 미칠 영향에 대한 전망으로 마무리
     5. 참고 자료: search.md에서 참고한 자료들을 링크로 제공
5. draft.md의 내용을 바탕으로 최종 블로그 포스트를 작성합니다.
   - 먼저 draft.md의 내용을 참고하여 각 문단마다 설명 보충과 이해를 돕기 위한 이미지를 gemini-image-gen 도구를 사용하여 생성합니다.
   - 생성된 이미지는 post/1.png, post/2.png...처럼 순서대로 이름을 사용해 저장합니다.
6. draft.md와 앞서 생성한 이미지들을 활용한 최종 블로그 포스트를 index.qmd에 작성합니다.
   - index.qmd의 헤더에는 embed-resources: true 설정을 추가하여 이미지가 포함되도록 합니다.
7. 마지막으로 quarto publish 도구를 사용하여 블로그 포스트를 게시합니다.
   - 예시: quarto publish gh-pages
```

```sh
LG AI 연구원에서 공개한 ‘엑사원 패스’에 대한 블로그를 작성해줘

업스테이지가 개발한 LLM 솔라 프로 2에 대한 블로그 글을 작성해줘
```
