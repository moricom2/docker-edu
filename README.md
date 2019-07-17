Windows 교육용 도커 실습 환경 설치
https://github.com/moricom2/docker-edu.git
=====================

### 1. 사전 요구 사항
Intel VT-x 또는 AMD AMD-v 활성화 및 지원 여부 확인

- cmd.exe (관리자 권한으로 실행)
> systeminfo  

다음과 같은 출력이 확인되어야 함  

>> Hyper-V 요구 사항: \n
>> &nbsp;&nbsp;&nbsp;&nbsp;VM 모니터 모드 확장: 예 \n
>> &nbsp;&nbsp;&nbsp;&nbsp;펌웨어에 가상화 사용: 예 \n
>> &nbsp;&nbsp;&nbsp;&nbsp;두 번째 수준 주소 변환: 예 \n
>> &nbsp;&nbsp;&nbsp;&nbsp;데이터 실행 방지 사용 가능: 예 \n

### 2. 지원되는 하이파바이저
VirtualBox(권장), Hyper-V

### 3. Chocolatey 설치 (package manager for Windows)
[choco](https://chocolatey.org/)

- cmd.exe 
> @"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"

### 4. VirtualBox 설치
[virtualbox](https://www.virtualbox.org/)
- cmd.exe
> choco install -y virtualbox virtualbox.extensionpack

### 5. Docker 컴포넌트 설치
[docker](https://www.docker.com/)
- cmd.exe
> choco install -y docker docker-machine docker-compose


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
#### vm 목록 확인
> docker-machine ls
#### vm 시작/중지
> docker-machine start/stop manager
#### set up the environment for the Docker client
> docker-machine env manager
- REM Run this command to configure your shell:
- REM     @FOR /f "tokens=*" %i IN ('"C:\ProgramData\chocolatey\lib\docker-machine\bin\docker-machine.exe" env manager') DO @%i

### 9. docker 클라이언트/서버 버전 확인
- cmd.exe
> docker version

