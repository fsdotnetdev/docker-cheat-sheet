# Docker Best Practise
ในการใช้งาน Docker ให้ได้ประสิทธิภาพดีที่สุดตามหลักของ Best Practise

## Table of Content
* Docker Image vs Dockerfile
* Clean Dockerfile
* Docker Repository
* Docker Command

## Clean Dockerfile
ในการเขียนคำสั่งลงใน Dockerfile ควรจะรวม Group ของ Command ไว้ด้วยกัน และควรเขียน Comment อธิบายคำสั่งต่าง ๆ ไว้ เพื่อให้สามารถทำความเข้าใจได้ง่าย
```bash
# Download Base Image Ubuntu Latest Version 16.04
FROM ubuntu:latest

# Update & Upgrade Ubuntu
RUN apt-get update && apt-get upgrade

# Install figlet, asciio, jp2a, cmatrix
RUN apt-get install -y figlet asciio jp2a cmatrix
```

## Build Image from Dockerfile
```bash
$ docker build -t [image_name] ./
```

## Credit
https://www.prontotools.io/%E0%B8%AA%E0%B8%A3%E0%B9%89%E0%B8%B2%E0%B8%87-docker-image-%E0%B8%9B%E0%B8%A3%E0%B8%B0%E0%B8%AA%E0%B8%B4%E0%B8%97%E0%B8%98%E0%B8%B4%E0%B8%A0%E0%B8%B2%E0%B8%9E/