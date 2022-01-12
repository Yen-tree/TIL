### Dumpdata & Loaddata

DB를 쓰다보면 여러가지 데이터를 옮겨야 하는 상황이 발생한다.

기존의 데이터를 옮기는 작업을 할때 장고(Django)의 manage.py에서 제공하는 dumpdata, loaddata 명령어를 통해 간편하게 옮길 수 있다.



> **dumpdata** 
>
> DB에 있는 데이터를 json형식 파일로 저장하는 것
>
> `python -Xutf8 manage.py dumpdata --indent 4 <app_name> > xxx.json`

>**loaddata**
>
>json파일을 장고 DB에 넣는 것
>
> `python manage.py loaddata <filename>`