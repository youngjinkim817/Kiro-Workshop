# Kiro IDE 인증

> Kiro IDE에 로그인하는 방법을 안내합니다.

## 지원하는 인증 방법

Kiro는 5가지 인증 방법을 지원합니다:

| 방법                             | 설명                                        |
| ------------------------------ | ----------------------------------------- |
| **GitHub**                     | GitHub 계정으로 로그인                           |
| **Google**                     | Google 계정으로 로그인                           |
| **AWS Builder ID**             | AWS Builder ID로 로그인 (AWS 계정 불필요)          |
| **AWS IAM Identity Center**    | 조직의 IAM Identity Center를 통한 로그인           |
| **External Identity Provider** | Microsoft Entra ID, Okta 등 외부 IdP를 통한 로그인 |

## 인증 순서

### 1. GitHub으로 로그인

1. Kiro IDE 실행 후 "**Sign in with GitHub**"를 선택합니다
2. 브라우저가 열리면 GitHub 계정으로 로그인합니다
3. `kirodotdev` 앱에 대한 권한을 승인합니다
4. Kiro IDE로 자동 돌아옵니다

### 2. Google로 로그인

1. "**Sign in with Google**"을 선택합니다
2. Google 계정을 선택하고 권한을 승인합니다

### 3. AWS Builder ID로 로그인

1. "**Login with AWS Builder ID**"를 선택합니다
2. 이메일과 비밀번호를 입력합니다
3. 접근 권한을 승인합니다

> **💡 참고** AWS Builder ID는 AWS 계정과 별개입니다. [profile.aws.amazon.com](https://profile.aws.amazon.com)에서 무료로 생성할 수 있습니다.

### 4. AWS IAM Identity Center로 로그인

1. 조직에서 제공한 **Start URL**과 **AWS Region**을 입력합니다
2. 조직의 인증 절차를 완료합니다

> **⚠️ 주의** AWS GovCloud(US) 리전은 IAM Identity Center 인증만 지원합니다. Kiro IDE 0.9.2+ 버전이 필요합니다.

### 5. External Identity Provider로 로그인

1. 회사 이메일을 입력하여 조직을 찾습니다
2. Microsoft Entra ID, Okta 등 조직의 IdP를 통해 로그인합니다

## 구독 및 무료 사용

Kiro는 **무료로 시작**할 수 있습니다. GitHub, Google, 또는 AWS Builder ID로 로그인하면 바로 사용 가능합니다.

> 자세한 내용은 [공식 인증 문서](https://kiro.dev/docs/getting-started/authentication/)를 참고하세요.
