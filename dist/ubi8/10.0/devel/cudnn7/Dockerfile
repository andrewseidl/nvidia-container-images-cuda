ARG IMAGE_NAME
FROM ${IMAGE_NAME}:10.0-devel-ubi8
LABEL maintainer "NVIDIA CORPORATION <sw-cuda-installer@nvidia.com>"

ENV CUDNN_VERSION 7.6.1.34
LABEL com.nvidia.cudnn.version="${CUDNN_VERSION}"

# cuDNN license: https://developer.nvidia.com/cudnn/license_agreement
RUN CUDNN_DOWNLOAD_SUM=af0791cba08468a4bf2a4ef15a787dac261f41219caaf335984d47d11eca19ba && \
    curl -fsSL http://developer.download.nvidia.com/compute/redist/cudnn/v7.6.1/cudnn-10.0-linux-x64-v7.6.1.34.tgz -O && \
    echo "$CUDNN_DOWNLOAD_SUM  cudnn-10.0-linux-x64-v7.6.1.34.tgz" | sha256sum -c - && \
    tar --no-same-owner -xzf cudnn-10.0-linux-x64-v7.6.1.34.tgz -C /usr/local && \
    rm cudnn-10.0-linux-x64-v7.6.1.34.tgz && \
    ldconfig