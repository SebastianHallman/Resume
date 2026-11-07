# Sebastian Hällman — CV

LaTeX source for my CV. GitHub Actions compiles the uploaded `resume.tex` as it is, without rewriting its content.

## Edit and build

Edit `resume.tex` and push your changes. GitHub Actions builds the PDF on every push, pull request, or manual run. No extra secrets are needed.

1. Open [Actions → Build CV PDF](https://github.com/SebastianHallman/Resume/actions/workflows/build-cv.yml).
2. Select the successful run for your latest commit.
3. Under **Artifacts**, download **Sebastian-Hallman-CV** and open `resume.pdf` inside the ZIP.

Artifact downloads require signing in to GitHub. Files are retained for 30 days; rerun the workflow to produce a fresh download. This setup does not publish to GitHub Pages, create a release, or commit generated PDFs.

For local builds, install a LaTeX distribution with `latexmk` and the packages used by `resume.tex` (on Ubuntu: `latexmk texlive-latex-extra texlive-fonts-recommended`). Then run:

```sh
latexmk -pdf -interaction=nonstopmode -halt-on-error -file-line-error -outdir=build -pdflatex="pdflatex -no-shell-escape %O %S" resume.tex
```

The PDF is written to `build/resume.pdf`. Generated files are ignored by Git.

## Privacy

The repository and its build artifacts are public. The generated PDF includes the personal information already present in `resume.tex`. Review both visible text and link destinations before pushing. Do not commit additional private files or build logs. Deleting a detail from the current file does not remove it from Git history.

## Template attribution

Based on [Sourabh Bajaj's resume template](https://github.com/sb2nov/resume), distributed under the MIT License. The original attribution remains in `resume.tex`, and the upstream license notice is preserved in `LICENSE`.

The license notice concerns the template; it does not imply endorsement or permission to impersonate the CV's subject.
