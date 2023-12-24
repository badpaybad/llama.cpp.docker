# llama.cpp

                    git clone https://github.com/ggerganov/llama.cpp.git

# download file bin to run first

                    curl -LO https://huggingface.co/jartine/llava-v1.5-7B-GGUF/resolve/main/llava-v1.5-7b-q4-server.llamafile

# docker cpu 


run docker 

                    docker build --no-cache -f dockerfile -t docker.io/dunp/llamacpp .
                    docker run  -d --restart always -p 8080:8080 --name llamacpp_8880 docker.io/dunp/llamacpp

# docker gpu 

dockerfile 

                    FROM nvidia/cuda:12.3.1-devel-ubuntu20.04

run docker 

                    sudo docker build --no-cache -f dockerfile -t docker.io/dunp/llamacpp .
                    sudo docker run --gpus all  -d --restart always -p 8080:8080 --name llamacpp_8880 docker.io/dunp/llamacpp
                    or
                    sudo docker run --gpus 0  -d --restart always -p 8080:8080 --name llamacpp_8880 docker.io/dunp/llamacpp

# install docker with gpu support                     

to find cuda lib version 

                    nvidia-smi 


https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/1.8.1/install-guide.html


to download install driver 

                    https://www.nvidia.com/Download/index.aspx?lang=en-us


instsall driver 

https://docs.nvidia.com/datacenter/tesla/tesla-installation-notes/index.html


                    sudo sh NVIDIA-Linux-x86_64-535.146.02.run

# nvidia docker file 

FROM nvidia/cuda:12.3.1-devel-ubuntu20.04

                    dockerfile 

                