# Subin Jin Academic Portfolio — al-folio v1.x custom build

이 패키지는 최신 al-folio v1.x 구조를 기준으로 만든 포닥 지원용 연구자 홈페이지입니다.
기본 al-folio의 publications / Jekyll / GitHub Pages 관리 방식은 유지하고, 첫 화면과 Research 페이지를 별도로 커스텀했습니다.

## 1. 가장 먼저 수정할 파일

### `_data/portfolio.yml`
홈페이지 문구 대부분이 여기에 있습니다.
- hero headline
- 첫 화면 설명
- 대표 성과 strip
- 3개 research theme
- future research vision
- selected work

### `_config.yml`
- 이름
- 웹사이트 주소
- 검색 키워드
- publication에서 강조할 저자명

### `_data/socials.yml`
- ORCID
- Google Scholar
- LinkedIn
- 이메일

## 2. 논문 추가

`_bibliography/papers.bib`에 BibTeX를 하나 추가하면 Publications 페이지에 자동으로 나타납니다.
대표 논문으로 강조하려면 항목에 아래를 추가합니다.

`selected={true}`

## 3. Figure 추가

이미지를 `assets/img/`에 넣습니다.
현재 첫 화면은 실제 Figure가 없어도 깨지지 않도록 추상적 material-interface visual을 CSS로 구현했습니다.
실제 대표 Figure가 정해지면 hero visual 또는 research card를 이미지 기반으로 교체하는 것을 권장합니다.

## 4. CV PDF

`assets/pdf/cv.pdf` 파일을 넣고 `_pages/cv.md` 하단의 주석 처리된 Download 버튼을 활성화합니다.

## 5. GitHub Pages 배포

가장 쉬운 방식:
1. GitHub에서 새 repository를 만듭니다. 개인 홈페이지라면 `YOUR_GITHUB_ID.github.io` 권장.
2. 이 폴더의 모든 파일을 repository에 업로드합니다.
3. `_config.yml`에서 `url:`을 `https://YOUR_GITHUB_ID.github.io`로 수정합니다.
4. GitHub → Settings → Pages에서 Source를 `Deploy from a branch`로 설정하고 `gh-pages` / root를 선택합니다.
5. main에 commit하면 `.github/workflows/deploy.yml`이 자동으로 사이트를 build하고 `gh-pages`에 배포합니다.

## 6. 수정 난이도

일상적으로 코드를 수정할 필요는 없습니다.
- 홈페이지 문구 → `_data/portfolio.yml`
- 논문 → `_bibliography/papers.bib`
- CV → `assets/pdf/cv.pdf`
- 연구 상세 내용 → `_pages/research.md`

GitHub 웹에서 연필 아이콘으로 파일을 수정하고 Commit changes를 누르면 자동 반영됩니다.

## 7. 공개 전 확인할 것

현재 이름과 공개 논문 정보는 확인된 자료를 바탕으로 넣었습니다. 아래 정보는 추정하지 않고 비워두었습니다.
- 이메일
- Google Scholar ID
- LinkedIn
- 최종 학위 수여일 / 세부 학력
- awards 전체 목록
- 실제 CV PDF
- 프로필 사진

이 항목들을 추가한 후 공개하는 것을 권장합니다.
