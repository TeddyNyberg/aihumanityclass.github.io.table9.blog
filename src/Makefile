###
### Makefile for building and pushing site
###

GITHUB_PAGES_BRANCH=gh-pages
THEME = aihum

MARKDOWN = python3 -m markdown
BASEDIR = .
LATEXDIR = $(BASEDIR)/latex
DOCSDIR = $(BASEDIR)/docs
PAGEDIR = $(BASEDIR)/content/

html:
	hugo --theme=$(THEME)

develop:
	sleep 1 && echo "Opening local browser..." &&  open http://localhost:1313 &
	hugo server --theme=$(THEME) --buildDrafts --renderStaticToDisk --printPathWarnings --printUnusedTemplates --watch

github: html
	cp -r ./public/* ../
	git add -A :/; git commit -m "Rebuilt site" ; git push

.PHONY: html clean develop
