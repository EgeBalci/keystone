# Go binding for Keystone engine. Remco Verhoef <remco@honeytrap.io>

ifndef BUILDDIR
OBJDIR = ./build
CGO_LDFLAGS = "-lkeystone -lstdc++ -lm"
else
OBJDIR = $(abspath $(BUILDDIR))/obj/bindings/go
endif

.PHONY: gen_const install clean check

gen_const:
	cd .. && python const_generator.py go
	go fmt

install:
	cd keystone && go build -a -ldflags '-s -w -extldflags "-static"'

clean:

check:
	cd keystone && go test
