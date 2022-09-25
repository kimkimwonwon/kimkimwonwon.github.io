# greedy 알고리즘

## 그리디 알고리즘이란

탐욕적으로 현재 주어진 문제를 당장에 좋은 것만 고르는 방법 매순간 가장 좋아 보이는 것을  고르는 알고리즘이다

거스름돈이 1260원이라고 할때, 돈을 500원 , 100원 ,10원으로 
가장 큰단위의 돈부터 거슬러 주면서 1260원을 모두 거슬러주는 것과 유사하다 
```python 

n= 1260 
count = 0

coin_types=[500,100,50,10]

for coin in coin_types:
    count += n//coin
    n%= coin

print(count)
```

코드의 시간 복잡도는 화폐의 종류가 (K) 라고 할때 O(K)이다. for문이 coin_types의 길이만큼 돌아가기 때문이다. 

## 그리디 알고리즘의 정당성
그리디 알고리즘은 그 해법이 정당한지 검토하는 과정을 거쳐야한다. 

거스름돈의 문제에서는 큰 단위가 항상 작은 배수의 배수형태이므로 최적해를 보장할 수 있는데, 아닌 경우도 있을 수 있다. 

## 큰수의 법칙 문제

주어진 수를 M번 더하여 가장 큰 수를 만드는 법칙 같은 수를 연속해서 K번을 초과하여 더해질 수 없다. 

```python
N M K 3개의 자연수, 공백으로 구분
N개의 자연수 
입력으로 주어지는 K는 항상  M보다 크거나 같다

입력예시 
5 8 3
2 4 5 4 6

출력예시 
46 
```

정답 



```python 
# N  M  K 를 공백으로 구분하여 입력받기
 n,m,k = map(int,input().split())
# N 개의 수를 공백으로 구분하여 입력받기

data = list(map(int,input().split()))

data.sort()

first = data[n-1]
second = data[n-2]

result= 0 

while True:
    for i in range(k):
        if m== 0 
            break
        m -= 1
    if m == 0:
        break

    result += second
    m-=1

print(result) 

```
나의 풀이는 큰값을 리스트 안에서 찾아내는 과정을 for 문으로 구하려고 했는데 정답에서는  list를 .sort로 정렬한 다음 index를 활용한 것이 훨씬 간결해서 좋은 것 같다.  나의 경우   그리고 m번 더하기 까지의 과정을 m을 줄여나가는 식으로 while문과 결합해서 break로 포문이 다 돌기전에 빠져나가게 구현해서 시간적으로 효율을 많이 보는 것 같다. 
