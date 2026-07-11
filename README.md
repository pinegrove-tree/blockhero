# 🧱 블록 히어로

9살 아이를 위해 만든 웹 브라우저용 블록 쌓기 게임입니다.
설치 없이 브라우저에서 바로 실행되고, `index.html` 파일 하나에 모든 코드(HTML/CSS/JS, 사운드까지)가 들어있습니다.

▶️ **플레이하기**: `https://<your-github-id>.github.io/<repo-name>/`
(배포 후 이 줄의 링크를 실제 주소로 바꿔주세요. 아래 "배포 방법" 참고)

## 게임 소개

떨어지는 블록을 움직이고 회전시켜서 가로 줄을 가득 채우면 그 줄이 사라지고 점수를 얻습니다.
줄을 많이, 연속으로, 한 번에 4줄(퍼펙트!)을 지울수록 더 큰 점수와 화려한 연출을 볼 수 있어요.

- 💣 **폭탄 블록**: 가끔 나타나요. 바닥에 닿으면 그 줄을 통째로 터뜨려요 (줄이 안 찼어도!)
- 🐌 **슬로우 블록**: 가끔 나타나요. 바닥에 닿으면 10초 동안 블록이 천천히 떨어져요
- 🎨 **테마 3종**: 네온 클래식(기본) · 공룡 정글(누적 5,000점) · 우주 탐험(누적 20,000점) — 누적 점수를 모으면 새 테마가 열려요
- 🎵 **오리지널 사운드**: 모든 효과음과 배경음악을 코드로 직접 만들었어요 (외부 음원 파일 없음)

## 조작법

| 키 | 동작 |
|---|---|
| ← → | 좌우 이동 |
| ↑ | 회전 |
| ↓ | 빨리 내리기 |
| Space | 순간 내리기 (쿵!) |
| C | 블록 보관(홀드) |
| P | 일시정지 |
| M | 음소거 켜기/끄기 |

## 기술 스택

- 순수 HTML / CSS / JavaScript (외부 라이브러리 0개)
- Canvas 2D API로 렌더링
- Web Audio API로 모든 사운드를 코드로 직접 생성 (오디오 파일 0개)
- `localStorage`에 최고 점수, 누적 점수, 테마 해금 상태, 선택한 테마, 음소거 설정을 저장

## 로컬에서 실행하기

파일을 그냥 더블클릭해서 열어도 되지만, 일부 브라우저 정책 때문에 로컬 서버로 여는 걸 추천합니다.

```bash
cd 프로젝트_폴더
python3 -m http.server 8000
# 브라우저에서 http://localhost:8000 접속
```

## 배포 방법 (GitHub Pages)

이 저장소 루트의 `index.html`을 GitHub Pages로 올리면 별도 빌드 과정 없이 바로 웹에서 플레이할 수 있습니다.

```bash
git init
git add index.html README.md
git commit -m "블록 히어로 초기 배포"
git branch -M main
git remote add origin https://github.com/<your-github-id>/<repo-name>.git
git push -u origin main
```

그다음 GitHub 저장소 페이지에서 **Settings → Pages** 로 이동해 Source를 `main` 브랜치, `/ (root)` 폴더로 설정하면
`https://<your-github-id>.github.io/<repo-name>/` 주소에서 몇 분 안에 게임이 열립니다.
