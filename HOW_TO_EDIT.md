# 사이트 수정 가이드 (brianew007.github.io)

GitHub에서 파일을 열고 연필 아이콘(Edit)으로 수정한 뒤 Commit하면, 2~4분 후 사이트에 자동 반영됩니다.
(진행 상황: 저장소의 **Actions** 탭 → "Deploy site")

## 자주 고칠 파일

| 바꾸고 싶은 것 | 파일 |
| --- | --- |
| 홈 화면 소개 글, 주소 | `_pages/about.md` |
| 프로필 사진 | `assets/img/prof_pic.jpg` 를 같은 이름의 사진으로 교체 (세로 4:5 정도 권장) |
| 논문 목록 | `_bibliography/papers.bib` |
| CV 내용 | `_data/cv.yml` |
| CV PDF 다운로드 버튼 | `assets/pdf/cv.pdf` 업로드 → `_pages/cv.md` 의 `# cv_pdf:` 줄 앞 `#` 삭제 |
| Research 페이지 | `_pages/research.md` |
| Experience 페이지 (TA, 발표 등) | `_pages/experience.md` — 아래쪽 `<!-- ... -->` 안의 템플릿을 꺼내 쓰면 됨 |
| 하단 아이콘 (이메일, Scholar, GitHub, ORCID 등) | `_data/socials.yml` |
| 이름 표기, 사이트 설명 | `_config.yml` 맨 위 (`first_name`, `last_name`, `description`) |
| 논문 목록에서 굵게 표시할 내 이름 | `_config.yml` 의 `scholar:` → `last_name`, `first_name` (bib 파일의 표기와 같아야 함) |

## 논문 넣기

1. Google Scholar 프로필 → 논문 목록 위 체크박스로 전체 선택 → **Export → BibTeX**
2. 나온 내용을 `_bibliography/papers.bib` 맨 아래에 붙여넣기
3. 홈 화면에 띄울 논문에는 `selected = {true},` 를 추가하고, `_pages/about.md` 의 `selected_papers: false` 를 `true` 로 변경
4. 선택 필드: `abbr = {JCP},` (저널 배지), `doi = {...},`, `bibtex_show = {true},`

## 주의

- `_config.yml` 의 `baseurl:` 줄은 비워 두되 지우지 말 것
- YAML 파일(`.yml`)은 들여쓰기(스페이스)가 중요함. 탭 사용 금지
- 빌드가 실패하면 Actions 탭의 빨간 X 를 눌러 로그 확인
