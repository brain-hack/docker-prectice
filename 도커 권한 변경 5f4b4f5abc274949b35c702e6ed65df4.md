# 도커 권한 변경

### 도커그룹생성

```bash
sudo groupadd docker
```

### 도커그룹에 유저추가

```bash
sudo usermod -aG docker ${USER}
#or
sudo gpasswd -a $USER docker
```

### 도커 재시작

```bash
sudo service docker restart
```

### 현재 사용자 로그아웃 및 재로그인

```bash
sudo su - // 루트사용자로 변경
su - {유저네임 예 : epsilondelta} // 사용자로 변경
```

### 테스트

```bash
docker run hello-world
```