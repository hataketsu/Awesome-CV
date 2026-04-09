.PHONY: cv.pdf

CC = xelatex
EXAMPLES_DIR = .
CV_DIR = ./cv
CV_SRCS = $(shell find $(CV_DIR) -name '*.tex')

cv.pdf: $(EXAMPLES_DIR)/cv.tex $(CV_SRCS)
	$(CC) -output-directory=$(EXAMPLES_DIR) $<
	mv $(EXAMPLES_DIR)/cv.pdf $(EXAMPLES_DIR)/hunganh.dev.pdf

clean:
	rm -rf $(EXAMPLES_DIR)/*.pdf
