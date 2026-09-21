# Graduate Final Exam — Research Paper Template

대학원 수업의 기말과제로 **자신만의 논문을 작성하기 위한 빈 LaTeX 양식**입니다.
IEEE 스타일의 letter 용지, 10pt, 2단 레이아웃을 사용합니다.
특정 연구 주제, 기존 논문의 본문·저자·실험 결과·그림·참고문헌·Git 이력은 포함하지 않습니다.
문서 안의 안내 문단, 그림, 수식, 표, 인용은 모두 교체용 더미입니다.

## 빠른 시작 — Overleaf

1. GitHub에서 **Use this template → Create a new repository**를 선택해 자신의 저장소를 만듭니다. Fork 대신 템플릿 기능을 사용하면 독립된 이력으로 시작할 수 있습니다.
2. 자신의 저장소에서 **Code → Download ZIP**으로 내려받습니다.
3. Overleaf에서 **New Project → Upload Project**로 ZIP을 올립니다.
4. Main document를 `main.tex`, Compiler를 **pdfLaTeX**로 설정하고 Recompile을 누릅니다.
5. 제목과 저자, `\thanks` 안의 소속·이메일을 바꾸고 `src/`의 각 문단을 자신의 글로 교체합니다.

`main.pdf`는 약 4쪽 분량의 더미 양식 미리보기입니다. 수정한 내용은 다시 컴파일해야 반영됩니다.

## 파일 구성

| 파일 | 역할 |
| --- | --- |
| `main.tex` | 제목·저자, 첫 페이지 좌하단 소속·이메일 각주, 패키지, 본문 연결 |
| `src/abstract.tex` | Abstract |
| `src/introduction.tex` | Introduction, 연구 질문과 기여 |
| `src/related_work.tex` | Related Work |
| `src/problem_formulation.tex` | 문제 정의와 표기 |
| `src/method.tex` | 제안 방법 |
| `src/experiments.tex` | 실험 설정과 결과 |
| `src/discussion.tex` | 해석과 한계 |
| `src/conclusion.tex` | 결론 |
| `figures/hook.tex` | Fig. 1: 첫 페이지 우상단의 핵심 아이디어 그림 |
| `figures/overview.tex` | Fig. 2: 두 번째 페이지 상단의 양단 너비 방법 개요 |
| `figures/component.tex` | Fig. 3: 개별 모듈의 내부 동작을 설명하는 상세도 |
| `figures/qualitative.tex` | Fig. 4: 정성적 비교 더미 그림 |
| `figures/sensitivity.tex` | Fig. 5: 파라미터 민감도·강건성 분석용 빈 플롯 |
| `tables/results.tex` | 수치를 채우지 않은 더미 결과표 |
| `tables/component_ablation.tex` | Table II: 구성요소 A/B 제거 ablation |
| `tables/design_ablation.tex` | Table III: 설계 대안별 성능·비용 ablation |
| `references.bib` | 가상 참고문헌 2개 — 실제 논문으로 교체 필수 |
| `ieeeconf.cls` | 레이아웃용 공용 LaTeX 클래스 |

## 로컬 컴파일

TeX Live 또는 MiKTeX에 `latexmk`와 필요한 패키지가 설치된 환경:

```sh
latexmk -pdf -interaction=nonstopmode -halt-on-error main.tex
```

`latexmk`가 없다면:

```sh
pdflatex -interaction=nonstopmode -halt-on-error main.tex
bibtex main
pdflatex -interaction=nonstopmode -halt-on-error main.tex
pdflatex -interaction=nonstopmode -halt-on-error main.tex
```

Tectonic 사용 시 `tectonic main.tex`로도 빌드할 수 있습니다.
`IEEEtran.bst`는 TeX 배포판의 IEEEtran 패키지에서 제공됩니다.

## 작성 및 제출 전 확인

그림은 `flafter`로 선언 위치보다 앞에 나오지 않도록 설정했습니다.
현재 더미 본문에서는 Fig. 1이 첫 페이지 우상단, Fig. 2가 두 번째 페이지 상단에 놓입니다.
본문이나 그림 크기를 크게 바꾸면 LaTeX의 자동 배치가 달라질 수 있으므로 최종 PDF를 확인하세요.

- 제목·이름·소속을 교체하고 안내 문장과 `DUMMY`, `Placeholder`, `[replace]`를 모두 제거합니다.
- 연구 질문 → 선행연구의 한계 → 제안 방법 → 검증 → 결론이 연결되도록 작성합니다.
- 그림과 표를 자신의 자료로 교체하고 본문에서 참조합니다. 표의 `---`는 0이 아니라 미측정입니다.
- 가상 참고문헌을 삭제하고 직접 확인한 실제 문헌만 인용합니다.
- 수행하지 않은 실험 결과를 만들지 않습니다. 제안 단계의 연구라면 평가 계획임을 명시합니다.
- 최종 PDF에서 인용, 수식, 그림, 표, 줄 넘침을 확인합니다.
- 페이지 제한, 마감일, 제출물, 평가 기준은 수업 공지를 따릅니다. 이 템플릿은 별도의 기준을 정하지 않습니다.

## 클래스 파일 고지

양식 유지에 필요한 `ieeeconf.cls`만 기존 양식에서 가져왔으며 수정하지 않았습니다.
해당 파일의 저작권·기여자·Perl Artistic License 고지를 그대로 보존했습니다.
그 외 모든 템플릿 파일은 수업용으로 새로 작성했습니다.
