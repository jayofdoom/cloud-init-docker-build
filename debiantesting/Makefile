IMAGE_UUID := $(shell uuidgen)
CONTAINER_UUID := $(shell uuidgen)

default: docker

docker:
	cat Dockerfile.debiantesting | docker build --no-cache -t "$(IMAGE_UUID)" -
	docker run --name="$(CONTAINER_UUID)" "$(IMAGE_UUID)" /bin/bash
	docker cp $(CONTAINER_UUID):/build/ .

clean:
	rm -rf ./build

echo:
	echo $(IMAGE_UUID)
	echo $(CONTAINER_UUID)
	echo $(PATH_TO_DEB)
