# docker-efk
Docker 기반의 ELK docker compose

# docker compose 실행
1. docker-compose 버전 확인
```shell
$ docker-compose --version

docker-compose version 1.23.2, build 1110ad01
```

2. docker-compose 컨테이너 생성 및 실행
```shell
$ docker-compose up

[+] Running 3/0
 ⠿ Container docker-efk-elasticsearch-1  Created                                                                                                      0.0s
 ⠿ Container docker-efk-kibana-1         Created                                                                                                      0.0s
 ⠿ Container docker-efk-fluentd-1        Created                                                                                                      0.0s
Attaching to docker-efk-elasticsearch-1, docker-efk-fluentd-1, docker-efk-kibana-1
docker-efk-fluentd-1        | 2023-02-22 13:51:50 +0000 [info]: init supervisor logger path=nil rotate_age=nil rotate_size=nil
docker-efk-fluentd-1        | 2023-02-22 13:51:50 +0000 [info]: parsing config file is succeeded path="/fluentd/etc/fluent.conf"
docker-efk-fluentd-1        | 2023-02-22 13:51:50 +0000 [info]: gem 'fluentd' version '1.15.3'
docker-efk-fluentd-1        | 2023-02-22 13:51:50 +0000 [info]: gem 'fluent-plugin-elasticsearch' version '4.0.1'
docker-efk-fluentd-1        | 2023-02-22 13:51:50 +0000 [info]: using configuration file: <ROOT>
docker-efk-fluentd-1        |   <source>
docker-efk-fluentd-1        |     @type tcp
docker-efk-fluentd-1        |     port 24224
```


3. send dummy json packet with nc via tcp
```shell
 h0422ys@DESKTOP-VERTEX  ~  echo '{"msg":"my name is minsu. thanks developer minsu"}' | nc localhost 24224
```


4. watch the result from kibana

<img width="795" alt="image" src="https://user-images.githubusercontent.com/37045096/220638811-e125de93-9edf-4db8-b2f0-931fe88e6d96.png">
