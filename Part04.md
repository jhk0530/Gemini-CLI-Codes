## Chapter 16

```sh
스테이블 코인 별 (USDT, USDC, DAI) 담보 구조, 투명성, 시장 규모, 규제 리스크, 기술적 안정성 등 핵심 요소를 객관적으로 비교 분석 해줘
```

```sh
mkdir stablecoin
cd stablecoin

mkdir .gemini
cd .gemini

touch GEMINI.md
cd ..

```

```sh
USDT, USDC, DAI에 대해 설명하는 공식 자료의 링크를 조사해줘
```

```markdown
## 자료 조사

- 조사 결과는 markdown 형식의 파일로 작성합니다.
- 조사의 각 항목마다 확인할 수 있는 링크를 표기합니다.

## 활용 자료

- 조사 과정에는 다음 웹페이지의 내용도 활용해야 합니다.

USDT (Tether)

- 공식 웹사이트: https://tether.to
- 백서 (Whitepaper): https://tether.to/en/whitepaper/
- 투명성 보고서: https://tether.to/en/transparency/

USDC (USD Coin)

- 공식 웹사이트: https://www.circle.com/en/usdc
- 개발자 문서: https://developers.circle.com/docs/usdc

DAI (Dai Stablecoin)

- 공식 웹사이트: https://makerdao.com/en/
- 개발자 문서: https://docs.makerdao.com/
```

```sh
스테이블코인에 대해 모르는 사람을 대상으로 전반적인 개요를 설명하고, 스테이블코인 별 (USDT, USDC, DAI) 담보 구조, 투명성, 시장 규모, 규제 리스크, 기술적 안정성 등 핵심 요소를 객관적으로 비교 분석하는 리서치 자료를 생성해 줘.
```

```sh
컨설팅 회사를 포함해 해외 주요 연구 기관 및 국책 기관에서 발간한 스테이블코인 관련 보고서를 찾아줘
```

```sh
@reports/에 있는 리포트들의 내용을 종합, 정리, 요약해 줘
이후 리포트에서 강조하는 주요 리스크 요인과, 회사에서 스테이블 코인을 활용하려 할 때 주의해야 할 포인트를 추가로 설명해줘
```

```sh
작성한 보고서를 옵시디언으로 옮겨줘.
```

## Chapter 17

```sh
quarto --version
```

```sh
@stablecoin_research.md를 참고해서 10분짜리 발표 자료를 Quarto와 reveal.js로 만들어 줘.
```

```sh
quarto render <SLIDEFILE>.qmd
```

```markdown
---
title: "스테이블코인: 기회와 리스크"
author: "Gemini"
format:
  revealjs:
    theme: sky
    embed-resources: true
    slide-number: true
---
```

## Chapter 18

```sh
git clone https://github.com/jhk0530/stablecoin-report.git
```

```sh
@stablecoin_presentation.html을 사용해서
@stablecoin-report에 github-page로 배포해 줘

@stablecoin_presentation.html을 사용해서 @stablecoin-report에 깃허브 페이지로 배포해줘.
```

## Chapter 19

```sh
현재 디렉터리에 있는 비행기 이미지의 내용을 확인해서 “항공사 - 항공사별 인덱스”의 형식으로 이름을 변경해줘. 파일 이름에는 공백이 없도록해
```

```sh
mkdir review
cd review
gemini
```

```sh
@Health_and_Personal_Care.jsonl 파일에서 title이나 text에 'price', 'recommend'가 들어간 리뷰들을 각각 price, recommend라는 디렉터리를 새롭게 만들고 그 안에 review.md라는 이름으로 저장해 줘. review.md에 저장할 때 원래 파일에서의 line number를 함께 저장해줘
```

```sh
@Health_and_personal_Care.jsonl 파일을 split 명령어를 사용해서 10000줄 단위로 분리한 다음 다시 작업해 줘.
```

```sh

#!/bin/bash

SCRIPT_DIR="/Users/<USERNAME>/Documents/geminiCLI/daily"

gemini -y -p "오늘의 주요 AI 뉴스를 요약해서 ${SCRIPT_DIR}/news-$(date +%y%m%d).md에 저장해줘"

crontab -e

0 9 * * * /Users/<USERNAME>/Documents/geminiCLI/daily/daily_news.sh

crontab -l

0 9 * * * /Users/<USERNAME>/Documents/geminiCLI/daily/daily_news.sh >> /Users/<USERNAME>/Documents/geminiCLI/daily/cron.log 2>&1

chmod +x /Users/<USERNAME>/Documents/geminiCLI/daily/daily_news.sh
```

```sh
export PATH=/usr/local/bin:/opt/homebrew/bin:$PATH
```

```sh
#!/bin/bash
export PATH=/usr/local/bin:/opt/homebrew/bin:$PATH
SCRIPT_DIR="/Users/<USERNAME>/Documents/geminiCLI/daily"
gemini -y -p "오늘의 주요 AI 뉴스를 요약해서 ${SCRIPT_DIR}/news-$(date +%y%m%d).md에 저장해줘"
```

## Chapter 20

```json
"notionMCP": {
  "command": "npx",
  "args": [ "-y", "mcp-remote", "https://mcp.notion.com/sse" ]
}

```

```sh
@250605\ 제 24회\ 국무회의록(용산).pdf

이 회의록 내용을 검토해서 요약해주고, 실행해야 할 액션 아이템과 예상 담당 부처(담당자)를 정리한 마크다운 표를 만들어줘.

표에는 액션 아이템, 담당자, 비고를 포함해야 해.

논의된 내용 중 AI와 관련된 내용은 별도의 항목으로 먼저 강조, 정리해 줘.

각 항목은 회의록의 논의 내용, 정책 방향, 추가 검토 요청 등을 반영해야 해.

결과는 노션에 새로운 문서로 저장해 줘
```

```sh
제미나이 CLI를 설명하는 글을 블로그 포스트, 이메일 뉴스레터, 보도자료 형식으로 각각 작성해서 마크다운으로 저장해줘
```

```sh
@google-gemini-gemini-cli.txt의 내용을 기반으로 제미나이 CLI를 설명하는 블로그 포스트를 작성해서 마크다운으로 저장해줘
```

```sh
@https://developers.google.com/newsletter/2825/06는 이전에 보낸 뉴스레터야, 이 뉴스레터의 구성과 글의 톤, 그리고 @google-gemini-gemini-cli.txt 이 내용을 참고하여 제미나이 CLI를 설명하는 이메일 뉴스레터를 작성해 줘.
```

```sh
여행자들이 현지인처럼 여행할 수 있도록 돕는 앱 아이디어가 있는데, 이걸 더 구체적인 기획안으로 발전시키고 싶어.
```

```markdown
## 기획안 리뷰

- 프로젝트 매니저, 개발자, 운영 매니저의 관점에서 기획안을 리뷰합니다.
- 개발자의 관점에서도 기획안을 리뷰합니다.
- 기획안 리뷰에서는 필요한 프레임워크와 방법론을 사용합니다.
- 기획안 리뷰는 기획안의 완성도를 높이고, 프로젝트의 성공 가능성을 높이는 데 중점을 둡니다.
```

```sh
@기획안.md에 있는 내용을 각 역할의 관점에서 리뷰해줘.
```

```sh
@feedback.md의 내용을 바탕으로 @기획한.md의 내용을 개선해줘
```

```sh
상세 기능 명세서와 사용자 흐름 및 와이어프레임, 그리고 정책 및 가이드라인을 각각 파일로 만들어 줘
```
