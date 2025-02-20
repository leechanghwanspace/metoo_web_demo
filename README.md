# 프로젝트 GitFlow 브랜치 전략 가이드
이 README는 우리 프로젝트에서 GitFlow 브랜치 전략을 어떻게 구현하고 사용해야 하는지에 대한 상세한 지침을 제공합니다. 모든 개발자는 이 가이드를 따라 일관된 브랜치 관리와 협업을 수행해야 합니다.

## 브랜치 구조 및 용도
### 1. main
- 목적: 안정적인 릴리즈 버전 유지.
- 사용: 릴리즈된 버전의 코드 저장소. 최종 사용자에게 배포되는 코드.
### 2. develop
- 목적: 다음 릴리즈 준비를 위한 개발 진행.
- 사용: 모든 개발이 이루어지는 기본 브랜치. 이곳에서 분기된 feature 브랜치가 병합되고, 준비된 코드는 release 브랜치로 이동.
### 3. feature
- 목적: 새 기능 개발, 기존 기능의 개선 및 버그 수정.
- 사용: develop 브랜치에서 분기하여 사용. 각 기능 또는 버그 수정에 대해 별도의 브랜치를 생성.
### 4. hotfix
- 목적: 릴리즈된 버전에서 발견된 긴급한 문제 해결.
- 사용: main 브랜치에서 직접 분기하여 긴급 수정 후 main과 develop에 병합.


## 상세 작업 절차
### 새 기능 개발
1. 브랜치 생성:
```bash
Copy code
git checkout develop
git pull origin develop
git checkout -b feature/기능명
```

2. 개발 작업 수행 후 커밋:

```bash
Copy code
git add .
git commit -m "새 기능: 기능명에 대한 설명"
```

3. 개발 브랜치로 병합 요청 (Pull Request):
- develop 브랜치로 Pull Request 생성.
- 동료의 코드 리뷰 후 병합 승인.

## 긴급 수정 (Hotfix)
1. Hotfix 브랜치 생성:
```bash
Copy code
git checkout main
git pull origin main
git checkout -b hotfix/버그명
```
2. 버그 수정 및 커밋:
``` bash
Copy code
git add .
git commit -m "긴급 수정: 버그명에 대한 설명"
```
3.병합 및 배포:
```bash
git push origin hotfix/버그명 ```