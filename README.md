# 1. 브랜치 및 머지 전략

Git Flow는 다양한 기능, 버그 수정, 릴리스를 관리하기 위한 브랜치 전략입니다.

## (1) 메인 브랜치

- `main` (또는 `master`): 항상 배포 가능한 상태로 유지되는 브랜치입니다. 모든 변경사항이 최종적으로 머지되는 브랜치입니다.
- `develop`: 개발이 진행되는 브랜치입니다. 기능들이 완성되면 이 브랜치로 머지되며, 주기적으로 `main`으로 머지됩니다.

## (2) 서브 브랜치

### [1] 기능 구현 브랜치(Feature Branches)

1. `develop`에서 `feature/[기능명]` 브랜치를 생성.
2. `feature/[기능명]`에서 플레이어 이동 기능을 개발.
3. 작업이 끝나면, `develop`브랜치로 머지.

### [2] 버그 수정 브랜치(Bugfix Branches)

1. `develop`에서 `bugfix/[버그명]` 브랜치를 생성.
2. 버그를 수정하고, `develop` 브랜치에 머지.

### [3] 릴리스 브랜치(Release Branches)

1. `develop`에서 `release/[버전명]` 브랜치를 생성.
2. 릴리스를 위한 최종 조정 및 버그 수정을 진행.
3. `release/[버전명]` 브랜치를 `main` 브랜치로 머지하고, 태그를 붙여 배포.

### [4] 핫픽스 브랜치 (Hotfix Branches)

1. `main`에서 `hotfix/[버그명]` 브랜치를 생성.
2. 긴급한 문제를 수정하고 `main` 및 `develop` 브랜치로 머지.

# 2. commit 규칙

## (1) 메시지 포맷

1. 헤더: 변경 내용 요약 (50자 이내)
2. 본문(선택사항): 변경 내용에 대한 설명 (필요시, 72자 정도로 줄 바꿈)
3. 커밋 타입
    - `feat`: 새로운 기능 추가
    - `fix`: 버그 수정
    - `docs`: 문서 수정
    - `refactor`: 코드 리팩토링 (기능 추가나 버그 수정 없이 코드 구조를 변경한 경우)
    - `style`: 코드 스타일 수정 (예: 들여쓰기, 공백, 세미콜론 추가 등)
    - `test`: 테스트 코드 추가나 수정
    - `chore`: 개발 도구나 환경 설정 변경, 번들링 등의 작업

## (2) 커밋 메시지의 구조

- 간결하고 명확하게: 커밋 메시지는 간단명료하고, 어떤 작업이 이루어졌는지 알 수 있어야 합니다.
- 현재형 사용: 커밋 메시지는 보통 현재형을 사용합니다. 예를 들어 "Fix bug" 또는 "Add feature" 등.
- 어떤 파일 또는 기능을 변경했는지 명확히: 커밋 메시지는 변경된 내용을 짧고 간단하게 설명해야 합니다.

## (3) 커밋 메시지 작성 예시

1. 새로운 기능 추가
    
    ```
    feat: Add player health system
    
    - Implemented health points and damage system for the player
    - Added UI element to display player health
    - Updated player death logic when health reaches zero
    ```
    
2. 버그 수정
    
    ```
    fix: Resolve player jump bug when colliding with platforms
    
    - Fixed the issue where player could get stuck in jumping state
    - Adjusted collision detection on platforms
    ```
    
3. 리팩토링
    
    ```
    refactor: Simplify enemy movement logic using a state machine
    
    - Replaced nested conditional logic with a state machine pattern
    - Improved readability and maintainability of the enemy AI code
    ```
    
4. 간단한 버그 수정
    
    ```
    fix: Resolve player jump bug when colliding with platforms
    
    - Fixed the issue where player could get stuck in jumping state
    - Adjusted collision detection on platforms
    ```
