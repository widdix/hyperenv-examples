FROM amazonlinux:2023
RUN curl -fsSL https://rpm.nodesource.com/setup_20.x | bash -
RUN yum install -y nodejs
RUN yum update -y
RUN yum install -y awscli unzip docker git tar
RUN if [ "$(uname -m)" == "x86_64" ]; then CPU_ARCH="amd64"; else CPU_ARCH="arm64"; fi && \
    cd /tmp && \
    curl -L -o tofu.zip "https://github.com/opentofu/opentofu/releases/download/v1.6.2/tofu_1.6.2_linux_${CPU_ARCH}.zip" && unzip tofu.zip && chmod +x tofu && mv tofu /usr/local/bin/ && rm -f *