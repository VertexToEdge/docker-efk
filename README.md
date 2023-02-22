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

Creating network "docker-elk_elk" with driver "bridge"
Building elasticsearch
Step 1/1 : FROM docker.elastic.co/elasticsearch/elasticsearch:7.8.1
 ---> a529963ec236
```


3. send dummy json packet with nc via tcp
```shell
 h0422ys@DESKTOP-VERTEX  ~  echo '{"msg":"my name is minsu. thanks developer minsu"}' | nc localhost 24224
```


4. watch the result from kibana

<img width="795" alt="image" src="https://user-images.githubusercontent.com/37045096/220638811-e125de93-9edf-4db8-b2f0-931fe88e6d96.png">
