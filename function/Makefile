PACKAGE=chimebot-whatsnew.zip
ZIP=zip

mkfile_path := $(abspath $(lastword $(MAKEFILE_LIST)))
current_dir := $(patsubst %/,%,$(dir $(mkfile_path)))

all: deps
	$(ZIP) -r $(PACKAGE) *

deps:
	docker run --mount type=bind,source="$(current_dir)",target=/app python \
		pip3 install -t . requests feedparser bs4
