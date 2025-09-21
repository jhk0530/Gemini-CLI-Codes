## Chapter 3

```sh
winget install Git.Git # Git Bash 설치 (Windows)
```

```sh
ls # Git Bash 명령어 작동 확인
```

```sh
pwd # 현재 경로 확인

ls -al # 현재 경로의 파일 및 폴더 확인

cd [폴더명] # 해당 폴더로 이동
cd .. # 상위 폴더로 이동
cd ~ # 홈 디렉토리로 이동
cd / # 루트 디렉토리로 이동
cd - # 이전 경로로 이동

mkdir [폴더명] # 폴더 생성

mv [기존이름] [새이름] # 파일 및 폴더 이름 변경

touch [파일명] # 빈 파일 생성
```

## Chapter 4

```sh
node -v
npm -v # Node.js 및 npm 버전 확인
```

```sh
systeminfo # windows 버전 확인
```

```sh
npm install -g @google/gemini-cli
sudo npm install -g @google/gemini-cli # 관리자 권한으로 실행
gemini --version # 제미나이 CLI 설치 및 버전 확인
```

```sh
gemini # 제미나이 CLI 실행
```

```sh
npm install -g @google/gemini-cli # 전역 설치
npm install @google/gemini-cli # 지역(로컬) 설치
npx https://github.com/google-gemini/gemini-cli # 설치 없이 실행
```

```sh
npm uninstall -g @google/gemini-cli # 전역 설치 삭제
npm uninstall @google/gemini-cli # 지역 설치 삭제
```

```sh
# 구글 클라우드 콘솔 설정
echo “export GOOGLE_CLOUD_PROJECT_ID=”이곳에 프로젝트 아이디를 입력합니다”” >> ~/.bashrc
source ~/.bashrc

# Gemini API Key 설정
echo ‘export GEMINI_API_KEY=”이곳에 제미나이 API KEY를 입력합니다”’ >> ~/.bashrc
source ~/.bashrc

# Vertex AI 설정
gcloud auth application-default login
echo ‘export GOOGLE_CLOUD_PROJECT=”이곳에 프로젝트 아이디를 입력합니다”’ >> ~/.bashrc
echo ‘export GOOGLE_CLOUD_LOCATION=”이곳에 프로젝트 경로를 입력합니다”’ >> ~/.bashrc
echo ‘export GOOGLE_GENAI_USE_VERTEXAI=true’ >> ~/.bashrc
source ~/.bashrc
```

```sh
# 프로젝트 폴더 내 환경 변수 설정
mkdir -p .gemini
echo ‘GOOGLE_CLOUD_PROJECT=”이곳에 프로젝트 아이디를 입력합니다”’ >> .gemini/.env

# 전역 환경 변수 설정
mkdir -p ~/.gemini
cat >> ~/.gemini/.env << ‘EOF’
GOOGLE_CLOUD_PROJECT=”이곳에 프로젝트 아이디를 입력합니다”
GEMINI_API_KEY=”your-gemini-api-key”
EOF
```

## Chapter 5

```sh
pwd # 현재 경로 확인

# 프로젝트 폴더 생성
mkdir gemini_proj
cd gemini_proj
gemini
```

```sh
안녕하세요 !

할 일 리스트 프로그램 만들어줘

계획대로 코드 구현 진행해

/quit
```
