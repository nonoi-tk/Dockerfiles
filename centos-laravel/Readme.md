## DockerFileのあるフォルダに移動
cd centos-laravel

## build
```
docker build --rm --no-cache -t centos-laravel .
```
しばらくまつとImageがビルド登録される

## create container
下記のコマンドでコンテナ起動
```
docker run --privileged --name centos-laravel -v /sys/fs/cgroup:/sys/fs/cgroup:ro -p 80:80 -d centos-laravel
```
DockerHubのGUIでもRUNできる

## connect container
接続
```
docker exec -it centos-laravel bash
```

## stop container
コンテナ終了
```
docker stop centos-laravel
```
