NAME=golang-slim
VERSION=1.12.0
TAG=$(VERSION)

.PHONY: build save clean

build:
	docker build -t $(NAME):$(TAG) .

save:
	docker save -o $(NAME)-$(TAG).tar $(NAME):$(TAG)

clean:
	rm *.tar
