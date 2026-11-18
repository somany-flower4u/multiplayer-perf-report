# 설원경 멀티플레이 서버 부하 시험 | Seolwongyeong Multiplayer Load Test

[한글 PDF](multiplayer-perf-report.ko.pdf) · [한글 LaTeX](multiplayer-perf-report.ko.tex)

[English PDF](multiplayer-perf-report.en.pdf) · [English LaTeX](multiplayer-perf-report.en.tex)

두 PDF는 2026년 11월 14일 운영 서버 부하 시험을 다룹니다. 한글 원고와 영어 번역은 측정표의 수치와 참고문헌을 공유합니다. 시스템 구성도와 운영 서버 그래프는 저장소의 기존 [이미지](../images/)를 사용합니다.

Both PDFs cover the November 14, 2026 production load test. The Korean and English sources share the benchmark table data and bibliography. Each edition uses the corresponding architecture diagram and capacity chart from the [repository images](../images/).

## 빌드 | Build

저장소 루트에서 실행합니다. Run from the repository root with TeX Live, XeLaTeX, BibTeX, and `latexmk`.

```sh
cd paper
latexmk -xelatex -no-shell-escape -interaction=nonstopmode -halt-on-error -file-line-error -outdir=build multiplayer-perf-report.ko.tex multiplayer-perf-report.en.tex
```

A minimal TeX Live installation also needs `amsmath`, `booktabs`, `caption`, `cite`, `enumitem`, `fancyhdr`, `fontspec`, `geometry`, `graphics`, `hyperref`, `ieeetran`, `kotex-utf`, `placeins`, `tex-gyre`, `titlesec`, `tools`, `unfonts-core`, `xcolor`, `xetexko`, and `xurl`.

## 정정 | Correction

한글 원문의 nginx CPU 사용량 비교를 정정했습니다. 1인당 CPU 사용량은 nginx 0.10%, Go 중계 0.14%입니다. 700명 단계의 실측값도 각각 73%와 101%로, nginx 사용량은 Go 중계의 약 70%입니다.

The source PDF overstated nginx CPU usage relative to the Go relay. The per-player estimates (0.10% and 0.14%) and the 700-player readings (73% and 101%) both put nginx at about 70% of the relay's usage.

Nistér와 Jändel의 참고문헌은 확인한 원고에 발행연도가 표시되지 않아 연도 미상으로 표기했습니다. The available Nistér and Jändel manuscript has no publication date, so both editions cite it as undated.
