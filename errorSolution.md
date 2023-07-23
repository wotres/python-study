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