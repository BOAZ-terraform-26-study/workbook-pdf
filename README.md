# workbook-pdf

주차별 워크북 `.md` 를 A4 PDF 로 뽑는 도구입니다.

```
markdown --(python-markdown)--> HTML + style.css --(Headless Chrome)--> PDF
```

## 준비물

- python3, `pip3 install markdown`
- Google Chrome (기본 경로가 아니면 `CHROME=/path/to/chrome` 로 지정)
- 폰트: Pretendard (본문), Menlo (코드). 없으면 시스템 폰트로 대체됩니다.

## 사용법

```bash
git clone https://github.com/BOAZ-terraform-26-study/workbook-pdf.git

# 디렉터리 안의 *.md 전부
./workbook-pdf/build-pdf.sh week6-import-drift/lecture

# 파일 하나
./workbook-pdf/build-pdf.sh week6-import-drift/lecture/개념워크북.md
```

PDF 는 각 `.md` 옆에 같은 이름으로 생깁니다. `.md` 를 고쳤으면 다시 돌려서 PDF 를 맞춥니다.

## 지원하는 문법

- GitHub alert (`> [!NOTE]`, `[!TIP]`, `[!IMPORTANT]`, `[!WARNING]`, `[!CAUTION]`)
- 표, 코드펜스, 상대 경로 이미지 (`./img/...`)
- 언어 태그 없는 코드펜스는 다이어그램/CLI 출력용 스타일로 표시
- A4 폭(96칸)을 넘는 코드블록은 해당 블록만 글자 크기를 줄여 맞춤
