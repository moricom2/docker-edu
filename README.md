윈도우 도커 실습 환경 설치
=====================

### 1. 사전 요구 사항
Intel VT-x 또는 AMD AMD-v 활성화 및 지원 여부 확인

- cmd.exe 
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

- PowerShell.exe
> Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))

### 4. VirtualBox 설치
[virtualbox](https://www.virtualbox.org/)

> choco install -y virtualbox virtualbox.extensionpack

### 5. docker 컴포넌트 설치
[docker](https://www.docker.com/)

> choco install -y docker docker-machine docker-compose


### (옵션) 6. Cmder 설치 (Portable console emulator for Windows)
[cmder](https://cmder.net/)

> choco install -y cmder


### (옵션) 7. Virtual Studio Code 설치 (Text Editor)
[vscode](https://code.visualstudio.com)

> choco install -y vscode
