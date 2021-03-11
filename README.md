# FaceNet-Docker

## Environment

- Xeon W-2140b
- NVIDIA QUADRO RTX4000
- Ubuntu 20.04(as docker host)
- Ubuntu 14.04(as container system)

## Use

1. Download CUDNN files and extract 'cuda' folder into FaceNet-Docker
2. run `docker builld .`
3. create container`docker container run -it --runtime=nvidia --privileged facenet0311 bash`
4. run code:)
