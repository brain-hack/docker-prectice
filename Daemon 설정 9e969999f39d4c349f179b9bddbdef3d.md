# Daemon 설정

### docker daemon 설정

```bash
sudo vi /etc/docker/daemon.json
```

```json
{
    "exec-opts": ["native.cgroupdriver=systemd"],
    "log-driver": "json-file",
    "log-opts" : {
        "max-size": "100m"
    },
    "data-root": "/mnt/storage/docker",
    "storage-driver": "overlay2"
}
```

![Untitled](Daemon%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8C%E1%85%A5%E1%86%BC%209e969999f39d4c349f179b9bddbdef3d/Untitled.png)

### Docker daemon service로 등록

```bash
sudo mkdir -p /etc/systemd/system/docker.service.d
```

### Docker daemon 재실행

```bash
sudo systemctl daemon-reload
sudo systemctl restart docker
```

![Untitled](Daemon%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8C%E1%85%A5%E1%86%BC%209e969999f39d4c349f179b9bddbdef3d/Untitled%201.png)

### 스토리지 설정 확인

```bash
sudo docker run hello-world
```

![Untitled](Daemon%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8C%E1%85%A5%E1%86%BC%209e969999f39d4c349f179b9bddbdef3d/Untitled%202.png)