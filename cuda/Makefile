CUDA_COMPILER=/usr/local/cuda-11.4/bin/nvcc
SRC_DIR = src/
all: clean archgpu

refgpu:
	$(CUDA_COMPILER) -o build/refgpu $(SRC_DIR)refgpu.cu -lcublas -lcudnn
	./build/refgpu

refcpu: 
	g++ -o build/refcpu $(SRC_DIR)refcpu.cpp -std=c++11
	./build/refcpu

archgpu:
	$(CUDA_COMPILER) -o build/archgpu $(SRC_DIR)archgpu.cu -lcublas -lcudnn 
	# ./build/archgpu 512 13 13 5 5 2

archcpu:
	g++ -o build/archcpu $(SRC_DIR)arch.cpp -std=c++11
	./build/archcpu	

clean:
	rm -f ./build/*
