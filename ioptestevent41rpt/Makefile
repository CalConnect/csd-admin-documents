SRC  := $(wildcard csd-*.adoc)
DOC  := $(patsubst %.adoc,%.doc,$(SRC))
XML := $(patsubst %.adoc,%.xml,$(SRC))
HTML := $(patsubst %.adoc,%.html,$(SRC))

SHELL := /bin/bash

all: $(HTML) $(XML) $(DOC)

clean:
	rm -f $(HTML) $(DOC) $(XML)

%.xml %.doc %.html: %.adoc
	bundle exec asciidoctor -b csd -r 'asciidoctor-csd' $^ --trace

# %.html: %.adoc
# 	bundle exec asciidoctor $^ --trace

open:
	open *.html

