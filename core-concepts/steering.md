# Steering (스티어링)

> Kiro에게 프로젝트에 대한 **지속적인 지식**을 제공하는 기능입니다.

![Steering](../.gitbook/assets/image-4.png)

## 세 가지 유형

### Always On (항상 활성)

모든 세션에서 로드됩니다. 코딩 표준, 기술 스택 정보, 팀 컨벤션 등에 사용합니다.

### Conditional (조건부)

일치하는 파일이 컨텍스트에 있을 때만 로드됩니다. 예: 테스트 파일을 편집할 때 테스트 가이드라인 로드.

### Manual (수동)

채팅에서 `#`으로 참조할 때만 로드됩니다. 항상 필요하지 않은 전문적인 컨텍스트에 사용합니다.

## 예시: 프로젝트 표준 문서

파일 위치: `.kiro/steering/standards.md`

```markdown
# Project Standards

- Use TypeScript for all source files
- Follow functional programming patterns
- Add JSDoc comments to exports
- Use Tailwind CSS for styling
- Write tests for all business logic
```

> **💡 참고** **자동 생성 기능**: Kiro Panel의 Steering 섹션에서 "Generate Steering Docs" 버튼을 클릭하면 프로젝트를 분석하여 자동으로 스티어링 문서를 생성합니다. 자세한 내용은 [공식 문서](https://kiro.dev/docs/steering/)를 참고하세요.
