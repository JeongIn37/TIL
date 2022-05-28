# K번째 약수

# 문제 개요

## 문제

<aside>
💡 어떤 자연수 p와 q가 있을 때, 만일 p를 q로 나누었을 때 나머지가 0이면 q는 p의 약수이다.

6을 예로 들면

- 6 ÷ 1 = 6 … 0
- 6 ÷ 2 = 3 … 0
- 6 ÷ 3 = 2 … 0
- 6 ÷ 4 = 1 … 2
- 6 ÷ 5 = 1 … 1
- 6 ÷ 6 = 1 … 0

그래서 6의 약수는 1, 2, 3, 6, 총 네 개이다.

두 개의 자연수 N과 K가 주어졌을 때, N의 약수들 중 K번째로 작은 수를 출력하는 프로그램을 작성하시오.

</aside>

## 입력

> 첫째 줄에 N과 K가 빈칸을 사이에 두고 주어진다. N은 1 이상 10,000 이하이다. K는 1 이상 N 이하이다.
> 

## 출력

> 첫째 줄에 N의 약수들 중 K번째로 작은 수를 출력한다. 만일 N의 약수의 개수가 K개보다 적어서 K번째 약수가 존재하지 않을 경우에는 0을 출력하시오.
> 

## 테스트 케이스 분석

### 입력
```
6 3
```

```
25 4
```

### 출력

```
3
```

```
0
```

---

# 문제 풀이

## 문제 해결 아이디어

나누어 떨어질 경우(약수) 리스트에 넣어두고 K번째(list[K-1])을 출력해야겠다

## 1차 시도

```python
# Your code here
N, K = map(int, input().split())
measure = []

for i in range(1, N+1):
    if N % i == 0:
        measure.append(i)
    else:
        continue

print(measure[K-1])
```

## 문제점 / 개선점

리스트를 사용하지 않고 다른 방법으로 시도해야겠다

---

## 2차 시도

```python
# Your code here
N, K = map(int, input().split())
cnt = 0

for i in range(1, N+1):
    if N % i == 0:
        cnt += 1
    if cnt == K:
        print(i)
```

## 문제점 / 개선점

강의를 보고 했더니 출력 예제를 6 3 만 봐서 0일 경우 예외처리를 안 했다

---

## 3차 시도

```python
# Your code here
N, K = map(int, input().split())
cnt = 0

for i in range(1, N+1):
    if N % i == 0:
        cnt += 1
    if cnt == K:
        print(i)
        break
else:
    print(0)
```
---

## 학습 내용

- for-else문
    
    : for문에서 break가 발생하지 않았을 경우의 동작을 else문에 적어줄 수 있다
