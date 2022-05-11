# 배포를 어떻게??


## 알파 테스트
알파 테스트를 목적으로 Jenkins - Docker  -Github 으로 구성하여 로컬에서 운영할 계획이다.

1. GitHub push
2. Detecting from Jenkins and Building a file
3. Docker build to image and run Container


```docker
FROM appinair/jdk11-maven

COPY 대상 앱.jar 목표 앱.jar

ENTRYPOINT ["java","-jar","/목표 앱.jar"]
```

```
docker build -t <이미지 이름>:<태그명> <Dockerfile 위치>

docker run -v D:/data/:/application_log -p 8081:8080 -d jartest:1
```


# Docker 업로드 방법

```
docker tag ebkm baugh248730/ebkm:1.0.0

docker push baugh248730/ebkm:1.0.0
```
## 베타 테스트

AWS EC2 로 전환하여 배포