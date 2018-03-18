# Dockerfile
Dockerfile เป็นเหมือน Shell Script บน Linux หรือ Bash Script บน Windows โดยการนำคำสั่งที่ต้องพิมพ์ลงบน Terminal มารวมอยู่ในไฟล์เดียวกัน Dockerfile ก็ทำงานคล้าย ๆ กัน แต่ใส่คำสั่งของ Docker เข้าไปแทน เพื่อใช้ในการสร้าง Image โดย Dockerfile มีขนาดเพียงไม่กี่ KB เทื่านั้น ถ้าเทียบกับ Image ที่มีขนาดหลาย MB

## Create Dockerfile
```bash
# Download Base Image Ubuntu Latest Version 16.04
FROM ubuntu:latest

# Update & Upgrade Ubuntu
RUN apt-get update && apt-get -y upgrade

# Install figlet, asciio, jp2a, cmatrix
RUN \
    apt-get install -y figlet && \ 
    apt-get install -y asciio && \
    apt-get install -y jp2a && \
    apt-get install -y cmatrix && \
    rm -rf /var/lib/apt/lists/*

# Add files.
ADD root/.bashrc /root/.bashrc
ADD root/.gitconfig /root/.gitconfig
ADD root/.scripts /root/.scripts

# Set environment variables.
ENV HOME /root

# Define working directory.
WORKDIR /root

# Define default command.
CMD ["bash"]
```

## Build Image from Dockerfile
```bash
$ docker build -t [image_name] ./
```

## Credit
