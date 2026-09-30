# 브랜치와 Pull Request 사용 가이드

브랜치와 Pull Request(PR)를 사용하면 변경 사항을 기본 브랜치와 분리해 작업하고, 병합하기 전에 다른 사람과 내용을 검토할 수 있습니다.

## 1. 작업 브랜치 만들기

먼저 최신 기본 브랜치에서 작업을 시작합니다. 저장소의 기본 브랜치가 `master`라면 아래의 `main`을 `master`로 바꿉니다.

```bash
git switch main
git pull
git switch -c feature/작업-이름
```

브랜치 이름은 변경 목적을 알아보기 쉽게 정합니다. 예를 들어 기능은 `feature/login`, 버그 수정은 `fix/login-error`처럼 쓸 수 있습니다.

## 2. 변경 사항 커밋하기

파일을 수정한 뒤 상태를 확인하고, 관련 파일을 커밋합니다.

```bash
git status
git add <파일>
git commit -m "로그인 기능 추가"
```

커밋 메시지는 변경 내용을 짧고 구체적으로 설명합니다.

## 3. 브랜치를 원격 저장소에 올리기

처음 푸시할 때 upstream을 설정합니다.

```bash
git push -u origin feature/작업-이름
```

## 4. Pull Request 만들기

GitHub 저장소에서 **Compare & pull request**를 선택하거나 **Pull requests → New pull request**로 이동합니다. 변경 브랜치를 기준 브랜치와 비교하도록 선택한 뒤 PR을 작성합니다.

PR에는 다음 내용을 적습니다.

- 무엇을 바꿨는지
- 왜 바꿨는지
- 검토자가 확인할 내용이나 실행 방법
- 관련 이슈가 있다면 `Closes #번호` 형식의 연결 문구

제목은 변경 내용을 요약하고, 본문에는 검토에 필요한 배경과 세부 사항을 담습니다.

## 5. Pull Request의 역사

GitHub는 2008년 2월 Pull Request 기능을 공개했습니다. 처음에는 저장소를 포크한 사람이 원본 저장소 관리자에게 자신의 변경 사항을 가져가 달라고 요청하거나, 별도 브랜치에 올린 기능을 알리는 방식으로 소개됐습니다. 이후 Pull Request는 변경 사항을 제안하고 함께 논의하는 협업 공간으로 자리 잡았습니다.

오늘날 GitHub의 Pull Request에는 변경 내용, 커밋 기록, 토론, 리뷰, 자동 검사 결과가 모입니다. 이를 통해 팀은 변경 사항의 배경과 진행 과정을 한곳에서 확인할 수 있습니다.

출처: [GitHub의 Pull Request 기능 소개 (2008년)](https://github.blog/news-insights/oh-yeah-there-s-pull-requests-now/)

## 전체 흐름 요약

```text
최신 main에서 브랜치 생성 → 수정 및 커밋 → 원격에 푸시 → Pull Request 작성
```
