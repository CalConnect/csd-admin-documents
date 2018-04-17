SRC  := $(wildcard csd-*.adoc)
XML  := $(patsubst %.adoc,%.xml,$(SRC))
HTML := $(patsubst %.adoc,%.html,$(SRC))

SHELL := /bin/bash

all: $(HTML) $(XML)

clean:
	rm -f $(HTML) $(XML) Gemfile Gemfile.lock

bundle:	Gemfile Gemfile.lock
	bundle

Gemfile Gemfile.lock:
	cp ../common/$@ .

%.xml %.html: %.adoc bundle
	bundle exec asciidoctor -b csd -r 'asciidoctor-csd' $< --trace

open:
	open $(HTML)

.PHONY: bundle all open
