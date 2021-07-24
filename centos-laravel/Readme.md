#build
docker build --rm --no-cache -t centos-laravel .

#create container
docker run --privileged --name centos-laravel -v /sys/fs/cgroup:/sys/fs/cgroup:ro -p 80:80 -d centos-laravel

#connect container
docker exec -it centos-laravel bash

#stop container
docker stop centos-laravel
