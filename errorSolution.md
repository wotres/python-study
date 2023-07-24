# 
* 상황
    * from datasets import load_dataset, DatasetDict 선언시
* 에러
    * ModuleNotFoundError: No module named '_lzma' 
* 원인
    * 일반적으로 Python이 lzma(xz) 압축 라이브러리를 지원하지 않고 컴파일될 때 발생
* 해결법
    * lzma 개발 라이브러리를 설치하고 Python을 다시 컴파일
    ```
    $ brew install xz
    $ pyenv uninstall <your_python_version>
    $ env LDFLAGS="-L/usr/local/opt/zlib/lib -L/usr/local/opt/sqlite/lib -L/usr/local/opt/xz/lib" pyenv install <your_python_version>
    $ pyenv virtualenv <new_python_version> <new_env_name>
    $ pyenv activate <new_env_name>
    ```

# 
* 상황
    * $pyenv activate <env_name> 수행시
* 에러
    * Failed to activate virtualenv.  
    Perhaps pyenv-virtualenv has not been loaded into your shell properly.  
    Please restart current shell and try again.
* 원인
    * 환경 변수가 잘못됨
* 해결법
    * .zshrc 환경 변수 추가
    ```
    $ export PYENV_ROOT="$HOME/.pyenv"
    $ export PATH="$PYENV_ROOT/bin:$PATH"
    $ eval "$(pyenv init --path)"
    $ eval "$(pyenv init -)"
    ```

# 
* 상황

* 에러

* 원인

* 해결법
