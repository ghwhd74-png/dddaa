# Git 브랜치 사용 가이드

브랜치는 하나의 저장소에서 작업 흐름을 나누는 기능입니다. 기능 개발이나 버그 수정을 별도 브랜치에서 진행하면 `main` 브랜치에 영향을 주지 않고 작업할 수 있습니다.

## 브랜치 확인

현재 브랜치와 작업 트리 상태를 확인합니다.

```bash
git status
git branch --list
```

## 브랜치 만들기

`feature-login` 브랜치를 만들고 바로 이동합니다.

```bash
git switch -c feature-login
```

이미 존재하는 브랜치로 이동하려면 다음 명령을 사용합니다.

```bash
git switch feature-login
```

## 변경 사항 저장하기

작업한 파일을 스테이징하고 커밋합니다.

```bash
git add <파일>
git commit -m "로그인 기능 추가"
```

## 브랜치 병합하기

작업을 마친 뒤 `main`으로 이동해 기능 브랜치를 병합합니다. 저장소의 기본 브랜치 이름이 `master`라면 `main` 대신 `master`를 사용합니다.

```bash
git switch main
git merge feature-login
```

## 병합된 브랜치 삭제하기

병합이 끝난 로컬 브랜치는 `-d` 옵션으로 삭제합니다. Git은 아직 병합되지 않은 커밋이 있으면 삭제를 거부합니다.

```bash
git branch -d feature-login
```

## 원격 저장소에 올리기

처음 원격에 브랜치를 올릴 때는 upstream을 설정합니다.

```bash
git push -u origin feature-login
```

이후에는 `git push`로 같은 브랜치의 변경 사항을 올릴 수 있습니다.
