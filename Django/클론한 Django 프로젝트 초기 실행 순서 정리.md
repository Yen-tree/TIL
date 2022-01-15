# 클론한 Django 프로젝트 초기 실행 순서 정리

### Python 가상환경 설정

1. 가상환경 생성 명령어

```
python -m venv venv
```

2. 가상환경 활성화

```
source venv/Scripts/activate
```

- 가상환경이 활성화 되면 터미널에 `(venv)` 가 생긴다.

3. `pip list` 나 `which python` 으로 가상환경이 제대로 설정되었는지 확인하기
4. (클론한 경우) requirements 설치

```
pip install -r requirements.txt
```

### migrate

1. migrations 파일 (설계도) 만들기

   ```
   python manage.py makemigrations
   ```

2. migrate: migrations 따라 db 그리기

   ```
   python manage.py migrate
   ```



### runserver

```
python manage.py runserver
```

