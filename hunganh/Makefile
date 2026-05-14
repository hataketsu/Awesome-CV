.PHONY: all clean

CC = xelatex
OUT_DIR = build
CV_SRCS = cv.tex $(wildcard cv/*.tex)
PDF = $(OUT_DIR)/cv.pdf

all: $(PDF)

$(PDF): $(CV_SRCS) awesome-cv.cls $(wildcard fonts/*.ttf) profile.jpg
	@mkdir -p $(OUT_DIR)
	$(CC) -interaction=nonstopmode -halt-on-error -output-directory=$(OUT_DIR) cv.tex
	@# Re-run to resolve page numbers / refs
	$(CC) -interaction=nonstopmode -halt-on-error -output-directory=$(OUT_DIR) cv.tex

clean:
	rm -rf $(OUT_DIR)
