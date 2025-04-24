FROM mcr.microsoft.com/devcontainers/base:ubuntu

ARG ARM_TOOLCHAIN_URL=https://developer.arm.com/-/media/Files/downloads/gnu-rm/5_4-2016q3/gcc-arm-none-eabi-5_4-2016q3-20160926-linux.tar.bz2?rev=111dee36f88b46728ac648cf41b4d375&revision=111dee36-f88b-4672-8ac6-48cf41b4d375?product=GNU%20Arm%20Embedded%20Toolchain%20Downloads,32-bit,,Linux,5-2016-q3-update

RUN dpkg --add-architecture i386 && \
    apt update && \
    apt dist-upgrade -y && \
    apt install -y libc6:i386 libstdc++6:i386
    #rm -rf /var/lib/apt/lists/*

RUN wget $ARM_TOOLCHAIN_URL -O gcc-arm-none-eabi.tar.bz2 && \
    tar -xjf gcc-arm-none-eabi.tar.bz2 && \
    rm gcc-arm-none-eabi.tar.bz2 && \
    mv gcc-arm-none-eabi-5_4-2016q3 /opt/gcc-arm-none-eabi-5_4-2016q3

ENV PATH="/opt/gcc-arm-none-eabi-5_4-2016q3/bin:${PATH}"

