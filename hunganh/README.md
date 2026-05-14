# Hung Anh Trinh — CV

<p align="center">
  <a href="https://github.com/hataketsu/Awesome-CV/actions/workflows/hunganh-cv.yml">
    <img alt="Build CV" src="https://github.com/hataketsu/Awesome-CV/actions/workflows/hunganh-cv.yml/badge.svg" />
  </a>
  <a href="https://github.com/hataketsu/Awesome-CV/releases/latest/download/hunganh-cv.pdf">
    <img alt="Download latest CV" src="https://img.shields.io/badge/CV-latest%20PDF-blue.svg" />
  </a>
  <a href="https://github.com/hataketsu/Awesome-CV/releases/latest">
    <img alt="Latest release" src="https://img.shields.io/github/v/release/hataketsu/Awesome-CV?label=release" />
  </a>
</p>

📄 **[Download latest CV (PDF)](https://github.com/hataketsu/Awesome-CV/releases/latest/download/hunganh-cv.pdf)**

Built from [`cv.tex`](cv.tex) with [Awesome-CV](https://github.com/posquit0/Awesome-CV) and XeLaTeX.

## Build locally

```bash
cd hunganh
make        # outputs build/cv.pdf
make clean
```

Requires `xelatex` + the Roboto / FontAwesome fonts bundled in `fonts/`. The easiest way is via the official TeX Live container:

```bash
docker run --rm -v "$PWD":/work -w /work/hunganh texlive/texlive:latest make
```

## Release pipeline

`/.github/workflows/hunganh-cv.yml` runs on every push touching `hunganh/**`:

| Trigger | Result |
| --- | --- |
| Push to `kube` / `master` | Build PDF + update rolling **`latest`** release |
| Tag `v*` or `cv-v*` | Build PDF + create matching GitHub Release |
| PR touching `hunganh/**` | Build PDF as artifact (no release) |
| Manual `workflow_dispatch` | Build PDF as artifact |

Released assets:

- `hunganh-cv.pdf` — stable filename for the badge / README link
- `hunganh-cv-<ref>-<sha>.pdf` — versioned copy

## Layout

```
hunganh/
├── cv.tex          # main document
├── cv/             # sections: summary, skills, experience, education, …
├── awesome-cv.cls  # template class (pinned copy)
├── fonts/          # bundled Roboto family
├── profile.jpg
└── Makefile        # xelatex build → build/cv.pdf
```
