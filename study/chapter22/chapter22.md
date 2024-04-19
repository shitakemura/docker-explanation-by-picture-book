# Chapter22

## 22.1

docker container run --name ruby --rm --interactive --tty --mount type=bind,source="$(pwd)",target=/my-work ruby:3.2.2 bash

ls /my-work/

ruby /my-work/hello.rb

rm /my-work/hello.rb
