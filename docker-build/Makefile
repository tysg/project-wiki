.PHONY: build run_unit_tests sh run_integration_tests build_debug

build: 
	docker build -t cs3203_spa:dev .

build_debug: 
	docker build -t cs3203_spa:dev --build-arg CMAKE_BUILD_TYPE=Debug .

run_unit_tests:
	docker run -it cs3203_spa:dev /data/Code00/build/src/unit_testing/unit_testing

run_integration_tests:
	docker run -it cs3203_spa:dev /data/Code00/build/src/integration_testing/integration_testing

sh:
	docker run -it \
		-v $(shell pwd)/Team00/Tests00:/data/Tests00 \
		-v $(shell pwd)/test_output:/data/test_output \
		-w /data/Tests00 \
		cs3203_spa:dev 


