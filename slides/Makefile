SLIDES_DIR := .
DOC        ?= main
OUTPUT     := $(SLIDES_DIR)/$(DOC).pdf
COMPOSE    := docker compose

.PHONY: all build image clean distclean pull open

all: build

image:
	$(COMPOSE) build

build: image
	DOC=$(DOC) $(COMPOSE) run --rm latex

clean:
	@echo "Removing auxiliary files…"
	@rm -f $(SLIDES_DIR)/$(DOC).aux \
	        $(SLIDES_DIR)/$(DOC).bbl \
	        $(SLIDES_DIR)/$(DOC).bcf \
	        $(SLIDES_DIR)/$(DOC).blg \
	        $(SLIDES_DIR)/$(DOC).fdb_latexmk \
	        $(SLIDES_DIR)/$(DOC).fls \
	        $(SLIDES_DIR)/$(DOC).log \
	        $(SLIDES_DIR)/$(DOC).nav \
	        $(SLIDES_DIR)/$(DOC).out \
	        $(SLIDES_DIR)/$(DOC).run.xml \
	        $(SLIDES_DIR)/$(DOC).snm \
	        $(SLIDES_DIR)/$(DOC).toc \
	        $(SLIDES_DIR)/$(DOC).vrb

distclean: clean
	@echo "Removing output PDF…"
	@rm -f $(OUTPUT)

pull:
	docker pull texlive/texlive:latest-small
	$(COMPOSE) build --no-cache

open: $(OUTPUT)
	open $(OUTPUT)
