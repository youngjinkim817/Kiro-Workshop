# AWS에 배포하기

> S3 + CloudFront로 퀴즈 앱을 호스팅합니다 — 몇 분 만에 라이브 URL을 얻을 수 있습니다.

> **⚠️ 주의** **참고**: 이 섹션은 AWS 자격 증명이 필요하므로 데모 시연용입니다.

## 배포 과정

### 1. CloudFormation 템플릿 생성

Kiro가 S3 버킷 + CloudFront 배포를 정의하는 Infrastructure-as-Code 템플릿을 생성합니다.

### 2. 스택 배포

하나의 명령으로 모든 리소스를 한 번에 생성합니다.

### 3. S3에 퀴즈 앱 업로드

Kiro가 `index.html`을 버킷에 동기화합니다.

### 4. CloudFront URL 열기

HTTPS가 적용된 라이브 URL로 퀴즈 앱이 인터넷에 공개됩니다.

## 배포 프롬프트

Kiro 채팅에 다음을 입력합니다:

```
Deploy my index.html as a static website on AWS using CloudFormation.
Create a CloudFormation template that sets up an S3 bucket, uploads
the file, and configures CloudFront with HTTPS. Then deploy the stack
and give me the live URL. No backend, no server — just static hosting.
```

## 아키텍처

```
사용자 브라우저 → CloudFront (CDN) → S3 Bucket (index.html)
```

> **💡 참고** **왜 CloudFormation인가?** CLI 명령을 하나씩 실행하는 대신, Kiro가 모든 인프라를 코드로 정의하는 템플릿을 생성합니다. 하나의 배포 명령으로 모든 것을 생성하고, 하나의 삭제 명령으로 모든 것을 제거합니다. 이것이 실제 AWS 팀의 작업 방식입니다.
