## Chapter 11

```json
{
  "name": "홍길동",
  "age": 30
}
```

```json
{
  "selectedAuthType": "oauth-personal",
  "theme": "Google Code",
  "preferredEditor": "vim",
  "vimMode": false,
  "ideMode": true
}
```

```sh
mkdir .gemini
cd .gemini
touch settings.json
```

```json
{
  "theme": "Ayu",
  "hideTips": true
}
```

```markdown
GEMINI_API_KEY = "my-api-key-1234" # 위험한 코드
```

```sh
export GEMINI_API_KEY="my-api-key-1234" # 환경 변수로 저장합니다.
```

```python
import os
API_KEY = os.getenv("GEMINI_API_KEY") # 환경 변수 이름으로 불러옵니다.
```

```markdown
GEMINI_MODEL=gemini-2.5-flash
NO_COLOR=1
```

```python
userName # 로어 카멜 케이스
UserName # 어퍼 카멜 케이스
user_name # 스네이크 케이스
user-name # 케밥 케이스
USER_NAME # 매크로 케이스
```

## Chapter 12

```sh
gemini --checkpointing
```

```json
{
  "checkpointing": {
    "enabled": true
  }
}
```

```sh
/restore <checkpoint_file>
```

```sh
square.py에서 모든 출력 내용을 영어로 변경해 줘
```

```sh
gemini --sandbox
gemini -s
```

```markdown
GEMINI_SANDBOX=true
```

```json
{
  "tools": {
    "sandbox": true
  }
}
```

## Chapter 13

```sh
/tools
```

```sh
mkdir bin
cd bin
touch get_tools
```

```sh
#!/bin/bash
cat <<EOF
[
  {
    "name": "echo",
    "description": "A tool that returns the input text as it is.",
    "parameters": {
      "type": "object",
      "properties": {
        "text": {
          "type": "string",
          "description": "The string to return."
        }
      },
      "required": ["text"]
    }
  }
]
EOF
```

```sh
#!/bin/bash
FUNC_NAME="$1"
shift
case "$FUNC_NAME" in
  echo)
    # Read parameters from stdin
    read INPUT_JSON
    # Extract text using jq
    TEXT=$(echo "$INPUT_JSON" | jq -r '.text')
    # Output result as JSON
    echo "{\"result\": \"$TEXT\"}"
    ;;
  *)
    echo "{\"error\": \"Unknown function: $FUNC_NAME\"}"
esac
```

```sh
chmod +x get_tools
chmod +x call_toll
```

```sh
mkdir .gemini
cd .gemini
```

```json
{
  "toolDiscoveryCommand": "bin/get_tools",
  "toolCallCommand": "bin/call_tool"
}
```

```markdown
## Echo

- echo 도구는 다음과 같이 사용합니다.
- 예시: echo "Hello, world!"
- 입력한 따옴표 안의 문자열을 그대로 반환합니다.
```

## Chapter 14

```json
{
  "theme": "Google Code",
  "selectedAuthType": "oauth-personal",
  "mcpServers": {
    "mcp-obsidian": {
      "command": "uvx",
      "args": ["mcp-obsidian"],
      "env": {
        "OBSIDIAN_API_KEY": "a250e7...689da2"
      }
    }
  }
}
```

```sh
brew install uv # macOS

curl -LsSf https://astral.sh/uv/install.sh | sh # 리눅스

powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex" # 윈도우

pip install uv # pip도 가능
```

```json
{
  "mcpServers": {
    "slack": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-slack"],
      "env": {
        "SLACK_BOT_TOKEN": "xoxb-your-bot-token",
        "SLACK_TEAM_ID": "T01234567",
        "SLACK_CHANNEL_IDS": "C01234567, C76543210"
      }
    }
  }
}
```

```json
{
  "mcp": {
    "inputs": [
      {
        "type": "promptString",
        "id": "slack_bot_token",
        "description": "Slack Bot Token (starts with xoxb-)",
        "password": true
      },
      {
        "type": "promptString",
        "id": "slack_team_id",
        "description": "Slack Team ID (starts with T)"
      }
    ],
    "servers": {
      "slack": {
        "command": "npx",
        "args": ["-y", "@modelcontextprotocol/server-slack"],
        "env": {
          "SLACK_BOT_TOKEN": "${input:slack_bot_token}",
          "SLACK_TEAM_ID": "${input:slack_team_id}"
        }
      }
    }
  }
}
```

## Chapter 15

```json
{
  "name": "my-extension",
  "version": "1.0.0",
  "mcpServers": {
    "my-server": {
      "command": "node my-server.js"
    }
  },
  "contextFileName": "GEMINI.md",
  "excludeTools": ["run_shell_command"]
}
```

```json
{
  "sandbox": true,
  "checkpointing": { "enabled": true },
  "contextFileName": "GEMINI.md"
}
```

```json
{
  "name": "test-automation",
  "version": "1.0.0",
  "mcpServers": {
    "test-runner": {
      "command": "python",
      "args": ["run_tests.py"],
      "cwd": "./ci/scripts"
    }
  },
  "contextFileName": "TEST_CONTEXT.md",
  "excludeTools": ["run_shell_command(rm -rf)", "WriteFileTool"]
}
```
