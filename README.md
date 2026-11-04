# 아영의 포트폴리오
전북대학교 컴퓨터공학·인공지능 전공 학생 심아영의 개인 소개 사이트
	사이트: https://ah0-say.github.io/ah0_sayprofile/
	저장소: https://github.com/ah0-say/ah0_sayprofile

## 사용 테마와 출처
- Hugo PaperMod: https://github.com/adityatelange/hugo-PaperMod
- 라이선스: MIT (루트의 LICENSE 파일 유지)
- 직접 작성한 부분: site/content/ 아래 글, site/pages.json 설정,
  site/assets/css/extended/profile-card.css, site/static/images/profile2.jpg

## 도구 버전
- Hugo extended 0.167.0
- Python 3.12
- (버전은 .github/workflows/hugo-pages.yml 기준)

## 로컬에서 빌드

# 1. 설치

```bash
winget install --id OpenJS.NodeJS.LTS -e
```

설치 후 Git Bash를 새로 열고 버전을 확인합니다.

실행 위치: 내 컴퓨터 · Git Bash

```bash
node -v
npm -v
```

확인: Node 24.x, npm 버전이 출력
출력: v24.20.0
	  11.19.0

## 2. 의존성 설치

실행 위치: 내 컴퓨터 · 저장소 루트 (`package.json`이 있는 폴더) · Git Bash

```bash
npm ci
```

확인: `node_modules/` 폴더가 생기고 `npx hugo version`에 `v0.167.0`이 나오면 됩니다. `package-lock.json`이 없으면 `npm install`을 사용합니다. `node_modules/`는 `.gitignore`로 제외됩니다.

## 3. 로컬에서 미리보기

실행 위치: 내 컴퓨터 · 저장소 루트 · Git Bash

```bash
npm run dev
```

확인: 브라우저에서 http://localhost:1313/ah0_sayprofile/ 을 열어 홈 화면이 보이면 됩니다. 파일을 저장하면 화면이 바로 바뀌고, `Ctrl + C`로 종료합니다.

## 4. 배포용 파일 빌드 (선택)

실행 위치: 내 컴퓨터 · 저장소 루트 · Git Bash

```bash
npm run build
```

확인: 저장소 루트에 `public/index.html`이 생성되면 됩니다.

## 수정할 파일 위치 
- 사이트 제목, 프로필, 링크 설정 : site/pages.json
- 소개 페이지 : site/content/about.md
- 활동 글 : site/content/posts/
- 소개 카드 스타일 : site/assets/css/extended/profile-card.css

## 수정 후 재배포
1. git add 수정한파일 (git add . (전체파일))
2. git commit -m "변경 내용 설명"
3. git push origin main 
4. GitHub Actions 탭에서 "Deploy Hugo to GitHub Pages"가 성공(초록 체크)했는지 확인
5. 시크릿 창에서 사이트를 열어 변경이 반영됐는지 확인