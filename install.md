# python env install 
## mac 설치
```
# brew install
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# python version 관리 
# pyenv 설치
$ brew install pyenv

# python package 격리
# virtualenv 설치
$ brew instll pyenv-virtualenv

# 환경 변수 등록
* ~/.zshrc 파일에 등록
```
$ export PYENV_ROOT="$HOME/.pyenv"
$ export PATH="$PYENV_ROOT/bin:$PATH"
$ eval "$(pyenv init --path)"
$ eval "$(pyenv init -)"
```
# 환경 변수 갱신
$ source ~/.zshrc
```

## pyenv 및 virtualenv 사용
```
# 설치 확인
$ pyenv --version

# 사용 가능한 Python 버전 나열
$ pyenv install --list

# 특정 Python 버전 설치
$ pyenv install <version>

# 설치된 Python 버전 나열
$ pyenv versions

# 전역 Python 버전 설정
$ pyenv global <version>

# 로컬 Python 버전 설정 ( 현재 디렉토리 python 버전설정)
$ pyenv local <version>

# 특정 Python 버전 제거
$ pyenv uninstall <version>

# 현재 Python 버전 확인
$ pyenv version

# 새 가상 환경 만들기
$ pyenv virtualenv <version> <env_name>

# 가상 환경 나열
$ pyenv virtualenvs

# 가상 환경 활성화
$ pyenv activate <env_name>

# 가상 환경 활성화
$ pyenv activate <env_name>

# 현재 가상 환경 비활성화
$ pyenv deactivate

# 가상 환경 삭제
$ pyenv uninstall <env_name>
```

## GPU 관련 설정 확인
```
import torch

# 사용 가능한 GPU 수 확인
print(torch.cuda.device_count())

# 현재 GPU 확인
print(torch.cuda.current_device())

# GPU의 이름 확인
print(torch.cuda.get_device_name(0)) # 0 is the device id

# cuda 사용 가능 확인
print(torch.cuda.is_available())

# 특정 gpu 여러개 사용 (ex 0, 2 gpu 사용)
import torch.nn as nn

model = Model()

if torch.cuda.is_available():
    print('CUDA is available. GPU operations possible.')
    if torch.cuda.device_count() > 1:
        print("Let's use", torch.cuda.device_count(), "GPUs!")
        model = nn.DataParallel(model, device_ids=[0, 2])
    else:
        torch.device('cuda')
else:
    print('CUDA is not available. GPU operations not possible. use CPU')
    torch.device('cpu')

model = model.to(device)


```

## GPU VS CUDA
* GPU는 병렬 처리 작업을 수행하는 물리적인 하드웨어이고, CUDA는 이러한 GPU를 프로그래밍하는 데 사용되는 소프트웨어 도구입니다. CUDA는 NVIDIA GPU에서만 실행
