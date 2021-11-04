## DockerFileのあるフォルダに移動
cd centos-laravel

## build
docker build --rm --no-cache -t centos-laravel .
しばらくまつとImageがビルド登録される

## create container
下記のコマンドでコンテナ起動
DockerHubのGUIでもRUNできる
docker run --privileged --name centos-laravel -v /sys/fs/cgroup:/sys/fs/cgroup:ro -p 80:80 -d centos-laravel

## connect container
あとは接続したり
docker exec -it centos-laravel bash

## stop container
コンテナ終了したり
docker stop centos-laravel
