ARG runtime="nvidia"
FROM nvidia/cuda:8.0-runtime-ubuntu16.04

LABEL maintainer="Chris Diehl <cultclassik@gmail.com>"

ENV NVIDIA_VISIBLE_DEVICES=0
ENV NVIDIA_DRIVER_CAPABILITIES="compute,utility"

ENV CMREL="https://s3-us-west-1.amazonaws.com/mastermine/minebox/claymore_Ethereum%2BDecred_Siacoin_Lbry_Pascal_gpu_v10.3_+LINUX.tar.gz"

ENV GPU_FORCE_64BIT_PTR=0
ENV GPU_MAX_HEAP_SIZE=100
ENV GPU_USE_SYNC_OBJECTS=1
ENV GPU_MAX_ALLOC_PERCENT=100
ENV GPU_SINGLE_ALLOC_PERCENT=100

RUN apt-get update && apt-get install -y --no-install-recommends \
    wget \
    ocl-icd-opencl-dev \
    libcurl3 \
 && rm -rf /var/lib/apt/lists/* \
 && mkdir /claymore \
 && wget --no-check-certificate $CMREL \
 && tar -xvf ./*.tar.gz -C /claymore --strip-components 1 \
 &&rm *.tar.gz \
 && chmod +x /claymore/ethdcrminer64

WORKDIR /claymore

EXPOSE 3333/tcp

ENTRYPOINT [ "/claymore/ethdcrminer64" ]
CMD [ "-epool", "mypool.org", "-ewal", "0xfdf87w987fw98" ]