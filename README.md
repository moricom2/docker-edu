##### https://github.com/moricom2/docker-edu.git #####
Windows 교육용 도커 실습 환경 설치
=====================

[도커허브](https://hub.docker.com/) & [깃허브](https://github.com/) 가입

### 1. 사전 요구 사항
Intel VT-x 또는 AMD AMD-v 활성화 및 지원 여부 확인

- cmd.exe (관리자 권한으로 실행)
> systeminfo  

다음과 같은 출력이 확인되어야 함  

>> Hyper-V Requirements:  
>> &nbsp;&nbsp;&nbsp;&nbsp;VM Monitor Mode Extensions: Yes  
>> &nbsp;&nbsp;&nbsp;&nbsp;Virtualization Enabled In Firmware: Yes  
>> &nbsp;&nbsp;&nbsp;&nbsp;Second Level Address Translation: Yes  
>> &nbsp;&nbsp;&nbsp;&nbsp;Data Execution Prevention Available: Yes 


### 2. 지원되는 하이파바이저
VirtualBox(권장), Hyper-V


### 3. Chocolatey 설치 (package manager for Windows)
[choco](https://chocolatey.org/)

- cmd.exe 
> @"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
#### choco로 설치한 패키지 목록 보기
> choco list --local-only


### 4. VirtualBox 설치
[virtualbox](https://www.virtualbox.org/)
- cmd.exe
> choco install -y virtualbox virtualbox.extensionpack


### 5. Docker 컴포넌트 설치
[docker](https://www.docker.com/)
- cmd.exe
> choco install -y docker-cli docker-machine docker-compose


### (옵션) 6. Cmder 설치 (Portable console emulator for Windows)
[cmder](https://cmder.net/)
- cmd.exe
> choco install -y cmder


### (옵션) 7. Virtual Studio Code 설치 (Text Editor)
[vscode](https://code.visualstudio.com)
- cmd.exe
> choco install -y vscode


### 8. docker Server 생성
[docker-machine](https://docs.docker.com/machine/reference/)
- cmd.exe
#### vm 생성 (생성하는 vm의 이름은 manager)
> docker-machine create --driver virtualbox manager  
or  
> docker-machine create --driver virtualbox --virtualbox-cpu-count "2" --virtualbox-memory "4096" manager  
#### vm 목록 확인
> docker-machine ls
#### vm 시작/중지
> docker-machine start/stop manager
#### set up the environment for the Docker client
> docker-machine env manager

다음과 같은 출력라인 확인후 copy&paste

>> REM Run this command to configure your shell:  
>> REM     @FOR /f "tokens=*" %i IN ('"C:\ProgramData\chocolatey\lib\docker-machine\bin\docker-machine.exe" env manager') DO @%i  


### 9. docker 클라이언트/서버 버전 확인
- cmd.exe
> docker version


## 실습용 코드 ## 
### docker-cli & Dockerfile로 스프링부트 이미지 빌드하기
https://github.com/moricom2/hello-rest.git  

### docker-maven-plugin으로 전자정부프레임워크 이미지 빌드하기
https://github.com/moricom2/egovframe-sample.git  


## CI서버 ## 
https://github.com/moricom2/jenkins.git  


### (추가) 머신의 리소스 수정 ###
> docker-machine stop manager  
> VBoxManage modifyvm manager --cpus 2  
> VBoxManage modifyvm manager --memory 4096  
> docker-machine start manager 

#### [도커컨테이너 교육 실습동영상 CICD 부분 요약 1](https://youtu.be/UEA3-v0r0uc)  

#### [도커컨테이너 교육 실습동영상 CICD 부분 요약 2](https://youtu.be/hpliqhWakKA)  

