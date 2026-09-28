# Hooks (훅)

> IDE를 위한 CI/CD처럼 작동하는 **이벤트 기반 자동화** 기능입니다.

![Hooks](../.gitbook/assets/image-1.png)

## 기본 패턴

```
WHEN 무언가가 발생하면 → THEN 자동으로 무언가를 수행
```

## 트리거 이벤트 (WHEN)

### 파일 이벤트

| 이벤트           | 설명          |
| ------------- | ----------- |
| `fileEdited`  | 파일이 수정되었을 때 |
| `fileCreated` | 파일이 생성되었을 때 |
| `fileDeleted` | 파일이 삭제되었을 때 |

### 에이전트 이벤트

| 이벤트            | 설명            |
| -------------- | ------------- |
| `promptSubmit` | 프롬프트가 제출되었을 때 |
| `agentStop`    | 에이전트가 중지되었을 때 |
| `preToolUse`   | 도구 사용 전       |
| `postToolUse`  | 도구 사용 후       |

### 수동 트리거

| 이벤트             | 설명                |
| --------------- | ----------------- |
| `userTriggered` | 사이드바의 버튼을 클릭하여 실행 |

## 예시: 접근성 자동 검사

파일 위치: `hooks/update-tests.json`

```json
{
  "name": "Update Tests on Change",
  "when": {
    "type": "fileEdited",
    "patterns": ["*.html", "*.css"]
  },
  "then": {
    "type": "askAgent",
    "prompt": "Check the code I just changed for accessibility issues and fix any problems you find."
  }
}
```

### 동작 흐름

```
파일 저장 → Hook 실행 → 에이전트가 접근성 검사 → 문제 수정 완료
```

> 자세한 내용은 [공식 문서](https://kiro.dev/docs/hooks/)를 참고하세요.
