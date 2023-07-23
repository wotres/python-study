# python env install 
## mac
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
$ echo 'if command -v pyenv 1>/dev/null 2>&1; then' >> ~/.zshrc
$ echo '  eval "$(pyenv init --path)"' >> ~/.zshrc
$ echo '  eval "$(pyenv virtualenv-init -)"' >> ~/.zshrc
$ echo 'fi' >> ~/.zshrc

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
