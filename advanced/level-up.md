# 레벨 업: 실전 프로젝트

> 퀴즈 앱을 한 단계 더 발전시켜 실제 백엔드에 연결합니다.

## 1단계: AWS 계정 + Bedrock 설정

1. AWS 콘솔에 접근합니다
2. 개인 개발 계정을 생성하거나 선택합니다
3. **Amazon Bedrock**으로 이동합니다 — 모든 모델이 기본적으로 활성화되어 있으며, 추가 설정이 필요하지 않습니다

## 2단계: 자격 증명 얻기

1. 계정에서 "**CLI Access**"를 클릭합니다
2. 3가지 옵션 중 **Option 1** (가장 쉬운 방법)을 선택합니다
3. Option 1 옆의 복사 버튼을 클릭합니다
4. 터미널을 열고 붙여넣기합니다 (`⌘ + V` → Enter)

> **💡 참고** **Option 1이 하는 일**: AWS 액세스 키, 시크릿 키, 세션 토큰을 환경 변수로 설정하는 3개의 export 명령을 복사합니다. 터미널에 붙여넣으면 AWS SDK가 인증할 수 있게 됩니다.

> **⚠️ 주의** **Option 1이 작동하지 않는 경우** Option 2를 시도하세요:

1. Option 2에서 자격 증명 블록을 복사합니다
2. 터미널에서 `mkdir -p ~/.aws`를 실행합니다
3. `open -a TextEdit ~/.aws/credentials`를 실행합니다
4. 자격 증명을 붙여넣고 저장합니다
5. "permission denied" 오류가 발생하면 `chmod 600 ~/.aws/credentials`를 실행합니다

## 3단계: Kiro로 빌드하기

1. Kiro에서 퀴즈 앱 프로젝트를 엽니다
2. 다음 프롬프트로 새 Spec을 생성합니다:

```
Add a Node.js backend that fetches quiz questions from
a DynamoDB table instead of the hardcoded array. Use
the AWS SDK v3. Keep the same frontend but load questions
from the API on start.
```

3. Kiro가 **Requirements → Design → Tasks**를 생성하도록 합니다
4. 태스크를 하나씩 실행합니다
5. 백엔드를 실행합니다: `node server.js`
6. `index.html`을 엽니다 — 퀴즈가 이제 DynamoDB에서 질문을 가져옵니다

> **💡 참고** **Bedrock 추론 프로필**: 모델을 호출할 때 기본 모델 ID 대신 크로스 리전 추론 프로필 ID를 사용하세요.

예시 (Claude Sonnet): `us.anthropic.claude-sonnet-4-20250514-v1:0`

모든 프로필은 Bedrock 콘솔의 **Cross-region inference**에서 확인할 수 있습니다.

## Kiro 방식의 개발

이것은 워크샵에서 배운 것과 동일한 워크플로우입니다:

1. Spec에서 원하는 것을 설명합니다
2. Kiro가 계획을 세우도록 합니다
3. 태스크를 실행합니다

유일하게 새로운 것은 백엔드를 실행하기 전에 터미널에 AWS 자격 증명이 있어야 한다는 점입니다. Kiro가 나머지를 처리합니다: 서버 코드 작성, DynamoDB 설정, 프론트엔드 업데이트.
