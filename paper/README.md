# 설원경 멀티플레이 서버 부하 시험 | Seolwongyeong Multiplayer Load Test

[한글 원본 PDF](multiplayer-perf-report.ko.pdf) · [한글 LaTeX](multiplayer-perf-report.ko.tex)

[English PDF](multiplayer-perf-report.en.pdf) · [English LaTeX](multiplayer-perf-report.en.tex)

한글 PDF는 최초 첨부된 원본입니다. 영문 PDF는 원본의 Pretendard 계열 서체, 페이지 여백, 표 양식과 저자–연도 인용을 따릅니다. 영문 PDF와 두 언어의 README에는 저장소의 [시스템 구성도와 운영 서버 그래프](../images/)를 사용했습니다.

The Korean PDF is the original file. The English translation follows its Pretendard typography, page margins, table styling, and author–date citations. The English PDF and both repository READMEs use the existing [architecture diagrams and capacity charts](../images/).

## LaTeX 조판본 빌드 | Build the LaTeX editions

아래 명령은 LaTeX 조판본을 `paper/build/`에 생성합니다. Run from the repository root with TeX Live, XeLaTeX, BibTeX, and `latexmk`.

```sh
cd paper
latexmk -xelatex -no-shell-escape -interaction=nonstopmode -halt-on-error -file-line-error -outdir=build multiplayer-perf-report.ko.tex multiplayer-perf-report.en.tex
```

A minimal TeX Live installation also needs `amsmath`, `booktabs`, `caption`, `cite`, `enumitem`, `fancyhdr`, `fontspec`, `geometry`, `graphics`, `hyperref`, `ieeetran`, `kotex-utf`, `placeins`, `tex-gyre`, `titlesec`, `tools`, `unfonts-core`, `xcolor`, `xetexko`, and `xurl`.

## 정정 | Correction

한글 원본 PDF 6절의 nginx CPU 비교에는 표현 오류가 있습니다. 1인당 CPU 사용량은 nginx 0.10%, Go 중계 0.14%입니다. 700명 단계의 실측값도 각각 73%와 101%로, nginx 사용량은 Go 중계의 약 70%입니다. 한글 README와 영문 PDF에 정정값을 반영했습니다.

Section 6 of the original Korean PDF overstated nginx CPU usage relative to the Go relay. The per-player estimates (0.10% and 0.14%) and the 700-player readings (73% and 101%) both put nginx at about 70% of the relay's usage. The Korean README and English PDF use the corrected comparison.

Nistér와 Jändel의 참고문헌은 확인한 원고에 발행연도가 표시되지 않아 영문 PDF에서 연도 미상으로 표기했습니다. The English PDF cites Nistér and Jändel's manuscript as undated.
