### 2023.02.16

## 코테
1. 시간복잡도
2. 자료구조(Stack, queue, hashmap, graph, tree)
3. 알고리즘(DFS, BFS, backtracking, DP, 순열조합)

## 이것이 코딩 테스트 준비 by 나동빈
1. 그리디
2. 구현
3. DFS/BFS

- 삼성전자 3시간 2문제//2문제<br>
- 카카오 5시간 7문제/1문제 //4문제<br>
- 라인 3시간 5문제 //3문제 6문제//4문제

### 1. 알고리즘 성능 평가
✔ 복잡도 = 알고리즘의 성능을 나타내는 척도
1. 시간 복잡도 = 특정한 크기의 입력에 대하여 알고리즘의 수행 시간 분석

2. 공간 복잡도 = 특정한 크기의 입력에 대하여 알고리즘의 메모리 사용량 분석<br>

✔ 복잡도가 낮을수록 좋은 알고리즘

✔ 빅오 표기법 -  가장 빠르게 증가하는 항만을 고려하는 표기법<br>
good-O(1)-O(logN)-O(N)-O(NlogN)-O(N^2)-O(N^3)-O(2^n)-bad<br>
상수시간 - 로그시간 - 선형시간 - 로그 선형 시간 - 이차 시간 - 삼차 시간 - 지수 시간
N,NlogN,N^2가 자주나옴
시간제한 대략 5초

### 2. 문제에서 가장 먼저 확인하는것 = 시간제한(수행시간 요구사항)
시간제한이 1초인 문제의 일반적인 기준<br>
N의 범위가 <br>
✔ 500 =>O(N^3)<br>
✔ 2000 => O(N^2)<br>
✔ 100000 => O(NlogN)<br>
✔ 10000000 =>O(N)

### 3. 알고리즘 문제 해결 과정 => 간결하게 짤 수 있다는 믿음 갖기
1. 지문 읽기 및 컴퓨터적 사고(쪼개기)
2. 요구사항(복잡도) 분석
3. 문제 해결을 위한 아이디어 찾기
4. 소스코드 설계 및 코딩

### 4. 자료형
✔ 정수형이 주로 출제<br>
✔ 지수표현방식(e,E)사용<br>
✔ INF = int(1e9)

✔ nxm  크기의 2차원 리스트
```python
n=4
m=3
array = [[0] * m for _ in range(n)]
```

✔ 리스트 관련 기타 메서드<br>
1. append() - O(1)

2. sort() - O(NlogN)
3. reverse() - O(N)
4. insert() - O(N)
5. count() - O(N)
6. remove() - O(N)

✔ sort() vs sorted()<br>

sort() - 값 변환해서 정렬 반환<br>
sorted() - 값 변환 x 정렬 반환

✔ 튜플은 리스트에 비해 상대적으로 공간 효율적이다.

### 5. 기본 입출력
✔ 자주 쓰는 입력

```python
map(int,input().split())
list(map(int,input().split()))
```

✔ 2차원 배열
```python
n=int(input())
m=int(input())
arr = []
for i in range(n)
    arr.append(list(map,int(input().split())))

```

✔ 입력을 최대한 빠르게 받기(그래프, 정렬)
```python
import sys
data=sys.stdin.readline().rstrip()
print(data)
```

✔ while문 보다는 for문이 더 간결한 경우가 많음<br>
✔ 무한루프는 거의 안씀

✔ 람다함수-익명함수<br>
한번쓰고 말때 주로 사용

### 6. 유용한 표준 라이브러리
1. itertools - 반복되는 형태의 데이터를 처리하는 기능을 제공하는 라이브러리(순열,조합)
2. heapq - 힙(heap) 기능을 제공하는 라이브러리, (우선순위 큐 구현시 사용)
3. bisect - 이진탐색 기능을 제공하는 라이브러리
4. collections - 덱(deque), 카운터(counter)등의 유용한 자료구조를 포함하고 있는 라이브러리

✔ 순열과 조합<br>

순열(P) - 서로 다른 n개에서 서로 다른 r개를 선택하여 일렬로 나열<br>
조합(C) - 서로 다른 n개에서 순서에 상관없이 서로 다른 r개를 선택하는 것

1. 순열
```python
from itertools import permutations
data=['A','B','C']
result=list(permutations(data,3))
print(result) //모든 순열 구하기
```
2. 중복순열(중복허용)
```python
from itertools import product
data=['A','B','C']
result=list(product(data,repeat=3)) // 2개를 뽑는 모든 순열 구하기
print(result)
```
3. 조합
```python
from itertools import combinations
data=['A','B','C']
result=list(combinations(data,2))
print(result) //모든 조합 구하기
```
4. 중복조합(중복허용)
```python
from itertools import combinations_with_replacement
data=['A','B','C']
result=list(combinations_with_replacement(data,2)) // 2개를 뽑는 모든 조합 구하기
print(result) 
```
