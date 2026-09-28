# MCP (Model Context Protocol)

> Kiro를 외부 도구와 데이터에 연결하는 **개방형 프로토콜**입니다.

![MCP](../.gitbook/assets/image-2.png)

## MCP란?

AI 도구가 외부 서비스(문서, API, 데이터베이스 등)와 통신할 수 있게 해주는 개방형 프로토콜입니다.

> **비유**: MCP는 AI를 위한 USB-C와 같습니다 — 하나의 표준 플러그로 다양한 장치를 연결합니다.

## 주요 특징

| 특징              | 설명                                                            |
| --------------- | ------------------------------------------------------------- |
| **실시간 지식**      | AWS 문서, GitHub, Jira 등을 연결하여 학습 데이터가 아닌 실제 데이터에 기반한 답변 제공     |
| **간단한 JSON 설정** | `.kiro/settings/mcp.json` 파일로 서버를 추가하거나, Power를 설치하여 설정 생략 가능 |
| **성장하는 생태계**    | 수백 개의 커뮤니티 MCP 서버 사용 가능. 로컬 및 원격 서버 모두 네이티브 지원                |

## 구조

```
🤖 Kiro 에이전트
  ↓ (학습 데이터를 넘어서는 정보 필요)
🔌 MCP 프로토콜 (도구 통신을 위한 표준 인터페이스)
  ↓
📄 AWS 문서 | 🔍 웹 검색 | 🗄️ 데이터베이스
```

## 설정 예시

파일 위치: `.kiro/settings/mcp.json`

```json
{
  "mcpServers": {
    "aws-docs": {
      "command": "uvx",
      "args": [
        "awslabs.aws-documentation-mcp-server@latest"
      ],
      "env": {
        "FASTMCP_LOG_LEVEL": "ERROR"
      },
      "disabled": false,
      "autoApprove": [
        "read_documentation",
        "search_documentation"
      ]
    }
  }
}
```

> 자세한 내용은 [공식 문서](https://kiro.dev/docs/mcp/)를 참고하세요.
