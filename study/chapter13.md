# Chapter13

## 13.1

docker image ls

## 13.2

docker image pull ubuntu:23.10

docker image pull ubuntu:22.04

docker image pull ubuntu:latest

docker image ls ubuntu

## 13.3

docker image pull ruby:3.2.2

docker image inspect ruby:3.2.2

docker container run --rm ruby:3.2.2 printenv RUBY_VERSION

docker container run --rm --interactive --tty ruby:3.2.2
