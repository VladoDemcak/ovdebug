# ovdebug
1.	Make sure you have openvino 2019R1 
2.	Make sure you have docker and docker-compose installed (versions of docker and docker-compose are in README file in github repository). Make sure nothing is running in docker with "docker ps -a"
3.	Make sure you have FPGA installed properly. 
```
aocl diagnose
```
should return board information and DIAGNOSTIC_PASSED message

4.	Clone repository with debug application: 
```
git clone https://github.com/VladoDemcak/ovdebug
```
5.	Change directory: 
```
cd ovdebug
```
6.	Run application with FPGA:  
```
python3 openvinotest.py -i videos/person-bicycle-car-detection.mp4 -m squeezenet1.1_FP16/squeezenet1.1.xml -d HETERO:FPGA,CPU
```
7.	Application should end successfully 
8.	Run docker compose: 
```
docker-compose up -d 
```
9.	Run application with FPGA again:  
```
python3 openvinotest.py -i videos/person-bicycle-car-detection.mp4 -m squeezenet1.1_FP16/squeezenet1.1.xml -d HETERO:FPGA,CPU
```
10.	If the application doesn’t freeze repeat step #9. 
11.	Remove kafka docker image: 
```
docker rm -f kafka 
```
12.	Run application with FPGA again:  
```
python3 openvinotest.py -i videos/person-bicycle-car-detection.mp4 -m squeezenet1.1_FP16/squeezenet1.1.xml -d HETERO:FPGA,CPU
```
13.	Application should work again without freezing.


```
$ docker version
Client: Docker Engine - Community
 Version:           19.03.1
 API version:       1.40
 Go version:        go1.12.5
 Git commit:        74b1e89
 Built:             Thu Jul 25 21:21:05 2019
 OS/Arch:           linux/amd64
 Experimental:      false

Server: Docker Engine - Community
 Engine:
  Version:          19.03.1
  API version:      1.40 (minimum version 1.12)
  Go version:       go1.12.5
  Git commit:       74b1e89
  Built:            Thu Jul 25 21:19:41 2019
  OS/Arch:          linux/amd64
  Experimental:     false
 containerd:
  Version:          1.2.6
  GitCommit:        894b81a4b802e4eb2a91d1ce216b8817763c29fb
 runc:
  Version:          1.0.0-rc8
  GitCommit:        425e105d5a03fabd737a126ad93d62a9eeede87f
 docker-init:
  Version:          0.18.0
  GitCommit:        fec3683
```

```
$ docker-compose --version
docker-compose version 1.24.0, build 0aa59064
```

Run #1.
```

```

Run #4.
```

```

Run #5.
```

```

Run #6.
```

```
