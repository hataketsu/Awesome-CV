.PHONY: hunganh.dev.cv.pdf

CC = xelatex
EXAMPLES_DIR = .
CV_DIR = ./cv
CV_SRCS = $(shell find $(CV_DIR) -name '*.tex')

hunganh.dev.cv.pdf: $(EXAMPLES_DIR)/hunganh.dev.cv.tex $(CV_SRCS)
	$(CC) -output-directory=$(EXAMPLES_DIR) $<

clean:
	rm -rf $(EXAMPLES_DIR)/*.pdf
