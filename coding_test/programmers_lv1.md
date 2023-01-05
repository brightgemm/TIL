# Programmers 코딩 테스트 연습



## 코딩테스트(Lv.1)

> 모든문제>안 푼 문제>난이도1>Python3>정답률 높은 순 정렬

### Day1


#### 짝수와 홀수

```python
def solution(num):
    return 'Odd' if num%2 != 0 else 'Even'
```

#### 약수의 합

```python
def solution(n):
    answer = 0
    for i in range(1,n+1):
        if n%i == 0:
            answer += i
    return answer
  
# 한줄로~
def solution(n):
  	return sum(k for k in range(1, n+1) if n%k ==0)
```

#### 평균구하기

```python
def solution(arr):
    return sum(arr)/len(arr)
```

#### 자릿수 더하기

```python
def solution(n):
    return sum([int(k) for k in str(n)])
```

​    

### Day2

#### 자연수 뒤집어 배열로 만들기

```python
## Mine
def solution(n):
    answer = [int(k) for k in str(n)]
    answer.reverse()
    return answer
  
  
## Others
def solution(n):
  	return [int(k) for k in reversed(str(n))]  #list.reversed() 활용
  	return [int(k) for k in str(n)][::-1]  #list슬라이싱 활용 [::-1] -> reversed와 동일한 효과
  
```

#### 정수 제곱근 판별

```python
def solution(n):
    return (n**0.5+1)**2 if (n**0.5).is_integer() else -1
```

#### 문자열 내 p와 y의 개수

```python
def solution(s):
    s = s.lower()
    return True if s.count('p') == s.count('y') else False
```

#### 문자열을 정수로 바꾸기

```python
def solution(s):
    return eval(s)
```

   

### Day3

#### 하샤드 수

```python
## Mine
def solution(x):
    return True if x%sum([int(k) for k in str(x)])==0 else False
  
  
## Others
def solution(x):
  	return x%sum(int(_) for _ in str(x)) == 0  #'==' 만으로도 일치불일치 비교 가능!
```

#### x만큼 간격이 있는 n개의 숫자

```python
## Mine
def solution(x, n):
    if x == 0:
        return [0 for k in range(n)]
    else:
        return [k for k in range(x, x*(n+1), x)]
      
      
## Others
def solution(x, n):
  	return [x+x*k for k in range(n)]
```

#### 정수 내림차순으로 배치하기

```python
def solution(n):
    return int(''.join(sorted(str(n), reverse=True)))
```

#### 나머지가 1이 되는 수 찾기

```python
def solution(n):
    answer = [k for k in range(1, n) if n%k == 1]
    return answer[0]
```

   

### Day4

#### 두 정수 사이의 합

```python
## Mine
def solution(a, b):
    if a>b:
        a, b = b, a
    return sum([k for k in range(a,b+1)])
```

#### 콜라츠 추측

```
1-1. 입력된 수가 짝수라면 2로 나눕니다. 
1-2. 입력된 수가 홀수라면 3을 곱하고 1을 더합니다. 
2. 결과로 나온 수에 같은 작업을 1이 될 때까지 반복합니다. 
3. 주어진 수가 1인 경우에는 0을, 작업을 500번 반복할 때까지 1이 되지 않는다면 –1을 반환
```

```python
## Mine
def solution(n):
    answer = 0
    for i in range(501):
        if n > 1:
            if n%2==0:
                n = n/2
                answer += 1
            else:
                n = n*3 + 1
                answer += 1
        else:
            break
    return -1 if answer > 500 and n!= 1 else answer
      
      
## Others
def solution(n):
    answer = 0
    while n != 1:
      	if n%2==0:
            n = n/2
        else:
            n = n*3+1
        answer += 1
        if answer >= 500:  #500번 이상인데 1이 안됐을 때
            return -1
    return answer
```

#### 서울에서 김서방 찾기

```python
def solution(seoul):
    return f'김서방은 {seoul.index("Kim")}에 있다'
```

#### 핸드폰 번호 가리기

```python
## Mine
def solution(phone_number):
    return '*'*(len(phone_number)-4)+phone_number[-4:]
  
  
## Others
# str.rjust() 활용
def solution(phone_number):
  	return phone_number[-4:].rjust(len(phone_number), '*')
  
# 문자열 정렬하기: ljust, center, rjust(len, fill_char)
s = '가나다라'
n = 7

s.ljust(n) # 좌측 정렬
s.center(n) # 가운데 정렬
s.rjust(n) # 우측 정렬
```

​    

### Day5

#### 나누어 떨어지는 숫자 배열

```python
# 방법1
def solution(arr, divisor):
    answer = [k for k in arr if k%divisor==0]
    answer.sort()
    return answer if len(answer) > 0 else [-1]
  
# 방법2
def solution(arr, divisor):
  	answer = sorted(filter(lambda x: x%divisor==0, arr))
    return answer if answer else [-1]  #if문에서 empty list는 False, 아니면 True 반환!
```

#### 제일 작은 수 제거하기

```python
def solution(arr):
    arr.remove(min(arr))
    return arr if arr else [-1]
```

#### 음양 더하기

```python
## Mine
def solution(absolutes, signs):
    answer = 0
    for i in range(len(absolutes)):
        if signs[i] == True:
            answer += absolutes[i]
        else:
            answer -= absolutes[i]
    return answer
  
  
## Others
# zip을 활용하여 리스트간 매칭
def solution(absolutes, signs):
  	return sum(absolutes if signs else -absolutes for absolutes, signs in zip(absolutes, signs))
  
# list(zip([1,2,3], ['a', 'b', 'c'])) -> [(1,'a'), (2,'b'), (3, 'c')] 

```

#### 없는 숫자 더하기

```python
## Mine
def solution(numbers):
    return sum(k for k in range(10) if k not in numbers)
  
  
## Others
  	return sum(filter(lambda x: x not in numbers, range(10)))
		return sum(range(10)) - sum(numbers)  #0~9까지의 합 - 있는 숫자의 합
```

   

### Day6

#### 가운데 글자 가져오기

```python
## Mine
def solution(s):
    mid = len(s)//2
    return s[mid] if len(s)%2!=0 else s[mid-1:mid+1]
  
  
## Others
# lambda함수 + 인자 넣기
def solution(s):
  	return (lambda x: s[x] if len(s)%2 != 0 else s[x-1: x+1])(len(s)//2)
```

#### 수박수박수박수박수박수?

```python
# 방법1
def solution(n):
    answer = '수'
    for i in range(n-1):
        if answer[-1] == '박':
            answer += '수'
        else:
            answer += '박'
    return answer

# 방법2: 홀짝 이용
def solution(n):
    return ''.join(['수' if k%2==0 else '박' for k in range(n)])
```

#### 내적

```python
# 방법1
def solution(a, b):
    return sum([a[i]*b[i] for i in range(len(a))])

# 방법2
def solution(a, b):
		return sum(x*y for x, y in zip(a, b))
```

#### 문자열 내림차순으로 배치하기

```python
def solution(s):
    return ''.join(sorted(s, reverse=True))
```

​    

### Day7

#### 문자열 다루기 기준

```python
def solution(s):
    return True if (len(s) == 4 or len(s)==6) and s.isdigit() else False
		return (len(s) == 4 or len(s)==6) and s.isdigit()
```

#### 약수의 개수와 덧셈

```python
## Mine
def solution(left, right):
    answer = 0
    for num in range(left, right+1):
        divisor = 0
        for i in range(1,num+1):
            if num%i==0:
                divisor += 1     
        if divisor%2==0:  #약수 개수가 짝수일 때
            answer += num
        else:  #약수 개수가 홀수일 때
            answer -= num
    return answer
  
  
## Others
# 제곱수는 약수는 홀수개, 나머지는 짝수개임을 이용
def solution(left, right):
    answer = 0
    for n in range(left, right+1):
        if (n**0.5).is_integer():
            answer -= n
        else:
            answer += n
    return answer
```

#### 부족한 금액 계산하기

```python
## Mine
def solution(price, money, count):
    answer = 0
    for i in range(count):
        answer += price + price*i
    return answer-money if answer > money else 0
  
  
## Others
def solution(price, money, count):
    price = sum(i*price for i in range(1, count+1))
    return max(price-money, 0)
```

#### 행렬의 덧셈

```python
# 방법1: numpy 활용
import numpy as np
def solution(arr1, arr2):
  	arr1, arr2 = np.array(arr1), np.array(arr2)
    return (arr1+arr2).tolist()

# 방법2: for문 활용
for row in range(len(arr1)):
    for col in range(len(arr1[0])):
        arr1[row][col] += arr2[row][col]
    return arr1
  
# 방법3: zip 활용
def solution(arr1, arr2):
    answer = []
    for a, b in zip(arr1, arr2):
        temp = []
        for c, d in zip(a, b):
            temp.append(c+d)
        answer.append(temp)
    return answer

# 방법4: zip list comprehension
def solution(arr1, arr2):
		answer = [[c + d for c, d in zip(a, b)] for a, b in zip(arr1, arr2)]
		return answer
```

​    

### Day8

#### 직사각형 별찍기

```python
# 방법1
n, m = map(int, input().split(' '))
for i in range(m):
    print(n*'*')

# 방법2
n, m = map(int, input().split(' '))
print((n*'*'+'\n')*m)
```

#### 최대공약수와 최소공배수

```python
# 방법1
from math import gcd
def solution(n, m):
    return [gcd(n, m), n*m/gcd(n,m)]
  
# 유클리드호제법으로 gcd함수 정의하기
def gcd(a, b):
  	a, b = b, a%b
    return a

# lcm 정의하기
def lcm(a, b):
  	return a*b/gcd(a, b)
```

#### 같은 숫자는 싫어(스택/큐)

```python
## Mine
def solution(arr):
    answer = [arr[0]]
		top = arr[0]
		for n in arr:
		    if top != n:
		        answer.append(n)
		        top = n
		return answer
  
  
## Others
# top 대신 list[-1]로 최상단 값 확인
def solution(arr):
    answer = [arr[0]]
    for n in arr:
        if answer[-1] != n:
            answer.append(n)        
    return answer
```

#### 이상한 문자 만들기

```python
def solution(s):
    sentence = []
    for word in s.split(" "):
        answer = ''
        for i in range(len(word)):
            if i%2 == 0:
                answer += word[i].upper()
            else:
                answer += word[i].lower()
        sentence.append(answer)
    return ' '.join(sentence)
  
# 문자열 앞뒤 공백, 연속 공백, 대소문자 섞여있는 경우를 모두 만족하자!
```

​     

### Day9

#### 3진법 뒤집기

```python
# 방법1: n진법 변환 함수 정의하기
def Notation(n, divisor): #n진법 변환하기
    tmp = ''
    while n:
        tmp += str(n%divisor)
				n = n//3
    return notation[::-1]  #거꾸로 해야 원래 n진법 표기!

def solution(n):
    return int(Notation(n, 3)[::-1], 3)
  
# 방법2: 3진법에만 해당하는 풀이
def solution(n):
    tmp = ''
    while n > 0:
        tmp += str(n%3)
        n = n//3
    return int(tmp, 3)
```

#### 예산

```python
## Mine
def solution(d, budget):
    answer = 0
    for i in range(len(d)):
        if sum(sorted(d)[:i+1]) <= budget:
            answer += 1
    return answer
  
  
## Others
def solution(d, budget):
    answer = 0
    for dept in sorted(d):
        budget -= dept
        if budget < 0:
            break
        answer += 1
    return answer
```

#### 시저 암호

```python
## Mine
def solution(s, n):
    abc = 'abcdefghijklmnopqrstuvwxyz'
    answer = ''
    for char in list(s):
        if char == ' ':
            answer += ' '
        elif char.islower():
            answer += abc[(abc.find(char)+n)%len(abc)]
        elif char.isupper():
            answer += abc[(abc.find(char.lower())+n)%len(abc)].upper()
            
    return answer
  
  
## Others
# 아스키코드 활용 - chr(number): 숫자를 문자로, ord('str'): 문자를 숫자로 변환
def solution(s, n):
    s = list(s)
    for i in range(len(s)):
        if s[i].isupper():
            s[i]=chr((ord(s[i])-ord('A')+ n)%26+ord('A'))
        elif s[i].islower():
            s[i]=chr((ord(s[i])-ord('a')+ n)%26+ord('a'))

    return "".join(s)
```

#### 최소직사각형(완전탐색)

```python
def solution(sizes):
    sizes = [[w, h] if w > h else [h, w] for w, h in sizes]
    return max(w for w, h in sizes)*max(h for w, h in sizes)
```

​    

### Day 10

#### 1차[비밀지도]

```python
## Mine
def solution(n, arr1, arr2):
    arr1 = [bin(x)[2:].zfill(n) for x in arr1]
    arr2 = [bin(y)[2:].zfill(n) for y in arr2]
    answer = []
    for i in range(n):
        row = ''
        for j in range(n):
            if arr1[i][j] == '0' and arr2[i][j] == '0':
                row += ' '
            else:
                row += '#'
        answer.append(row)
    return answer


## Others
# ''.join()사용해서 리스트 안에 작성할 수도 있음
def solution(n, arr1, arr2):
    arr1 = [bin(x)[2:].zfill(n) for x in arr1]
    arr2 = [bin(x)[2:].zfill(n) for x in arr2]
    return [''.join(' ' if arr1[i][j]=='0' and arr2[i][j] =='0' else '#' for j in range(n)) for i in range(n)]
  
  
# str.zfill(len): 문자열에 인수로 넣은 값의 자리수만큼 0 채우기
'1234'.zfill(8)   #'00001234'
'-1234'.zfill(8)   #'-0001234'

# str.rjust(len, [fill_char]): 문자열에 길이만큼 지정 문자 채우기(디폴트 = ' ')
'1234'.rjust(8)   #'    1234'
'1234'.rjust(8, '0')   #'00001234'
'1234'.rjust(8, 'a')   #'aaaa1234'
```

#### 문자열 내 마음대로 정하기

```python
def solution(strings, n):
    return sorted(strings, key=lambda x: (x[n], x))
```

   

### Day11

#### k번째수(정렬)

```python
## Mine
def solution(array, commands):
    answer = []
    for x in commands:
        temp = sorted(array[x[0]-1:x[1]])
        answer.append(temp[x[2]-1])
    return answer
  
# 다듬기!
def solution(array, commands):
    return [sorted(array[x[0]-1:x[1]])[x[2]-1] for x in commands]
```

#### 숫자 문자열과 영단어

```python
## Mine
def solution(s):
    num_dict = {'zero': 0, 'one': 1, 'two': 2, 'three': 3, 'four': 4, 'five': 5, 'six': 6, 'seven': 7, 'eight': 8, 'nine': 9}
    for num in num_dict:
        if num in s:
            s = s.replace(num, str(num_dict[num]))
    return int(s)

  
## Others
# dict.keys() 활용
def solution(s):
    num_dict = {'zero': 0, 'one': 1, 'two': 2, 'three': 3, 'four': 4, 'five': 5, 'six': 6, 'seven': 7, 'eight': 8, 'nine': 9}
    for key in num_dict.keys():
        s = s.replace(key, num_dict.get(key))
    return int(s)
  
# list.index() 활용
def solution(s):
    num_list = ['zero', 'one', 'two', 'three', 'four', 'five', 'six', 'seven', 'eight', 'nine']
    for num in num_list:
        if num in s:
            s = s.replace(num, str(num_list.index(num)))
    return int(s)
```

​    

### Day12

#### 삼총사

```python
from itertools import combinations
def solution(number):
    answer = 0
    for i in combinations(numbers, 3):
        if sum(i) == 0:
            answer += 1
    return answer

# 다듬기!
def solution(number):
    return sum(1 for k in combinations(number, 3) if sum(k)==0) 
```

#### 두 개 뽑아서 더하기

```python
## Mine
from itertools import combinations
def solution(numbers):
    return sorted(list(set(sum(k) for k in combinations(numbers, 2)))
                  
                  
## Others
# combinations()없이
def solution(numbers):
    answer = []
    for i in range(len(numbers)-1):
        for j in range(i+1, len(numbers)):
            answer.append(numbers[i]+numbers[j])            
    return sorted(list(set(answer)))
```

​    

### Day13

#### 2016년

```python
# 방법1
def solution(a, b):
    months = [31, 29, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
    days = ['FRI', 'SAT', 'SUN', 'MON', 'TUE', 'WED', 'THU']  #1/1금요일부터
    return days[(sum(months[:a-1]) + b)%7-1]

# 방법2: datetime 모듈
from datetime import datetime
def solution(a, b):
    week = ['MON', 'TUE', 'WED', 'THU', 'FRI', 'SAT', 'SUN']
    return week[datetime(2016, a, b).weekday()]

# datetime.weekday(): 월0 ~ 일6
# datetime.isoweekday(): 월1 ~ 일7
```

#### 포켓몬(해시)

```python
## Mine
def solution(nums):
    if len(set(nums)) <= len(nums)//2:
        return len(set(nums))
    else:
        return len(nums)//2

# 다듬기!
def solution(nums):
    return len(set(nums)) if len(set(nums)) <= len(nums)//2 else len(nums)//2
  
  
## Others
def solution(nums):
  	return min(len(set(nums)), len(nums)//2)  #위 조건문 단순화 버전
```



### Day14

#### 소수찾기

```python
## Mine
# 에라토스테네스의 체
def solution(n):
    answer = [1 for k in range(n+1)]
    for i in range(2, int(n**0.5)+1):  #제곱근까지 검사
        if answer[i] == 1:  #소수일 때
            j = 2
            while i*j <= n:
                answer[i*j] = 0  #가장 작은 i를 제외한 배수(=i로 나누어 떨어짐) 지우기
                j += 1
    return sum(answer[2:])  #0, 1을 제외한 2부터의 소수 개수
  
  
## Others
# 에라토스테네스의 체(set 사용하여 간단 구현)
def solution(n):
    prime = set(range(2, n+1))  #가장 작은 소수인 2부터 n까지 담은 집합
    for i in range(2, int(n**0.5)+1):  #제곱근까지 검사
        if i in prime:
        	prime -= set(range(i*2, n+1, i))  #i의 배수 제거하기
    return len(prime)
  
  
'''
# 효율성 문제에 대한 고민
- 소수를 찾기 위해 n이하의 모든 수를 다 나눠서 진행하는 건 효율성이 나쁨
- 2를 제외한 모든 짝수는 합성수
- n이하의 소수는 제곱근 n 이하의 숫자 중 소수로 나누어떨어지지 않는 수
  예를 들어 n=100 일 때, 10이하의 숫자 중 가장 작은 소수만 남기고 배수를 거르는 형태
'''
```

#### 모의고사(완전탐색)

```python
## Mine
def solution(answers):
    students = ['12345', '21232425', '3311224455']
    answer = []
    for i in students:
        score = 0
        for j in range(len(answers)):
            if str(answers[j]) == i[j%len(i)]:
                score += 1
        answer.append(score)
        
    return [k+1 for k in range(len(answer)) if answer[k]==max(answer)]
  
  
# 수정: enumerate 사용하여 인덱스 번호로 활용하기
def solution(answers):
    students = ['12345', '21232425', '3311224455']
    scores = [0] * len(students)
    for i, student in enumerate(students):
        for j, answer in enumerate(answers):
            if student[j%len(student)] == str(answer): scores[i] += 1

    return [i+1 for i in range(len(scores)) if scores[i]==max(scores)]
```

​    

### Day15

#### 소수 만들기

```python
## Mine
from itertools import combinations
def solution(nums):
    nums = [sum(k) for k in combinations(nums, 3)]
    answer = 0
    for i in nums:
        answer += 1
        for j in range(2, int(i**0.5)+1):
            if i%j==0:
                answer -= 1
                break
    return answer


## Others
# 방법1: 이중 for문
from itertools import combinations
def solution(nums):
    answer = 0
    for i in combinations(nums, 3):
        answer += 1
        num = i[0] + i[1] + i[2]  #num = sum(i)로 변경
        for div in range(2, int(num**0.5)+1):
            if num % div == 0:
                answer -= 1
                break
    return answer

  
# 방법2: 소수 판별 함수 작성(제곱근까지 조사하여 복잡도 줄이기)
from itertools import combinations
def isPrime(num):
    for i in range(2, int(num**0.5)+1):
        if num % i == 0:
            return 0
    return 1

def solution(nums):
    return sum(1 for k in combinations(nums, 3) if isPrime(sum(k)))  #세 개의 합이 소수이면 +1
```

#### 실패율

```py
## Mine
# 방법1
def solution(N, stages):
    answer = {}
    for stage in range(1, N+1):
        fail, total = 0, 0
        for user in stages:
            if user == stage:  #스테이지에 도전한 사람 중 실패한 사람은 스테이지 번호와 동일함. 작으면 아직 미도전, 크면 클리어 함
                fail += 1
            if user >= stage:  #스테이지에 도전 중인 사용자
                total += 1
        answer[stage] = fail/total if total > 0 else 0
    
    return sorted(answer, key=lambda x: answer[x], reverse=True)
  	# list comprehension 표현법
    return [k for k, v in sorted(failrate.items(), key=lambda x:-x[1])]

 
# 방법2
def solution(N, stages):
    answer = {}
    total = len(stages)
    for stage in range(1, N+1):
        if total == 0:
            answer[stage] = 0
        else:
            cnt = stages.count(stage)  #클리어못한 사용자
            answer[stage] = cnt/total
            total -= cnt  #이전스테이지를 클리어 못한 사용자 제거
    return sorted(answer, key=lambda x: answer[x], reverse=True)
```

​    

### Day16

#### 콜라 문제

```python
## Mine
def solution(a, b, n):
    result = 0
    while n >= a:
        result += (n//a)*b
        n = n%a + (n//a)*b
    return result
```



#### [1차] 다트 게임

- [입출력 예제]

  | 예제 | dartResult | answer | 설명                        |
  | ---- | ---------- | ------ | --------------------------- |
  | 1    | `1S2D*3T`  | 37     | 11 * 2 + 22 * 2 + 33        |
  | 2    | `1D2S#10S` | 9      | 12 + 21 * (-1) + 101        |
  | 3    | `1D2S0T`   | 3      | 12 + 21 + 03                |
  | 4    | `1S*2T*3S` | 23     | 11 * 2 * 2 + 23 * 2 + 31    |
  | 5    | `1D#2S*3S` | 5      | 12 * (-1) * 2 + 21 * 2 + 31 |
  | 6    | `1T2D3D#`  | -4     | 13 + 22 + 32 * (-1)         |
  | 7    | `1D2S3T*`  | 59     | 12 + 21 * 2 + 33 * 2        |

```python
## Mine
import re
def solution(dartResult):
		# 점수 계산
    scores = list(zip(re.findall(r'\d+', dartResult), re.findall("['S', 'D', 'T']", dartResult)))
    rule = {'S': 1, 'D': 2, 'T': 3}
    scores = [int(x)**rule.get(y) for x, y in scores]
    
    # *, #은 [2], [4,5], [6,7,8]번 자리에 올 수 있음
    for i, c in enumerate(dartResult):
        if c == '*':
            if i <= 2:
                scores[0] *= 2
            elif 3 < i < 6:
                scores[0], scores[1] = scores[0]*2, scores[1]*2
            elif i >= 6:
                scores[1], scores[2] = scores[1]*2, scores[2]*2

        if c == '#':
            if i <= 2:
                scores[0] *= -1
            elif 3 < i < 6:
                scores[1] *= -1
            elif i >= 6:
                scores[2] *= -1

    return sum(scores)
  
  
## Others
def solution(dartResult):
    answer, idx, b_score = 0, 0, 0
    while idx < len(dartResult):
        score = 10 if dartResult[idx+1].isdecimal() else int(dartResult[idx])  #점수가 10인 경우와 아닌 경우
        idx += 2 if dartResult[idx+1].isdecimal() else 1  #10인 경우와 아닌 경우 보너스 문자열 찾기
        bonus = (lambda x : 3 if x=='T' else 2 if x=='D' else 1)(dartResult[idx])
        idx += 1
        
        if idx == len(dartResult) or dartResult[idx].isdecimal():  #옵션 없는 경우
            answer += score**bonus
            b_score = score**bonus
        elif dartResult[idx] == '#':
            answer += -score**bonus
            b_score = -score**bonus
            idx += 1
        else:  #'*'인 경우
            answer += b_score + 2*score**bonus
            b_score = 2*score**bonus
            idx += 1
        
    return answer

# 점수가 10인 경우 replace로 처리
def solution(dartResult):
    scores, answer = [], []
    dartResult = dartResult.replace('10','k')  #점수가 10인 경우 예외처리
    scores = ['10' if i == 'k' else i for i in dartResult]
    
    i = -1
    sdt = {'S': 1, 'D': 2, 'T': 3}
    for s in scores:
        if s.isdecimal():
            answer.append(int(s))
            i += 1
        elif s in sdt :
            answer[i] = answer[i] ** (sdt[s])
        elif s == '*':
            answer[i] = answer[i] * 2
            if i != 0 :
                answer[i-1] = answer[i-1] * 2
        elif s == '#':
            answer[i] = answer[i] * (-1)
            
    return sum(answer)
  
# re 활용
import re
def solution(dartResult):
    bonus = {'S' : 1, 'D' : 2, 'T' : 3}
    option = {'' : 1, '*' : 2, '#' : -1}
    p = re.compile('(\d+)([SDT])([*#]?)')  #(모든 숫자), (SDT), (*#)가 0 또는 1인 경우
    dart = p.findall(dartResult)  #ex) [('1', 'S', ''), ('2', 'D', '*'), ('3', 'T', '')]
    
    for i in range(len(dart)):
        if dart[i][2] == '*' and i > 0:
            dart[i-1] *= 2
        dart[i] = int(dart[i][0]) ** bonus[dart[i][1]] * option[dart[i][2]]
        
    return sum(dart)
```



### Day17

#### 로또의 최고 순위와 최저 순위

- [입출력 예]

  | lottos                | win_nums                 | result |
  | --------------------- | ------------------------ | ------ |
  | [44, 1, 0, 0, 31, 25] | [31, 10, 45, 1, 6, 19]   | [3, 5] |
  | [0, 0, 0, 0, 0, 0]    | [38, 19, 20, 40, 15, 25] | [1, 6] |
  | [45, 4, 35, 20, 3, 9] | [20, 9, 3, 45, 4, 35]    | [1, 1] |

```python
## Mine
def solution(lottos, win_nums):
    win = set(lottos)&set(win_nums)
    minimum, maximum = 7-len(win), 7-len(win)-lottos.count(0)
    return [min(6, maximum), min(6, minimum)]
  
  
## Others
def solution(lottos, win_nums):
    rank=[6,6,5,4,3,2,1]
    cnt_0 = lottos.count(0)
    win = 0
    for x in win_nums:
        if x in lottos:
            win += 1
    return rank[cnt_0 + win],rank[win]
```



### Day18

#### 푸드 파이트 대회

```python
## Mine
def solution(food):
    result = ''
    for i, n in enumerate(food):
        if i > 0: 
          result += str(i)*(n//2)
    return '0'.join([result, result[::-1]])

                     
## Others
def solution(food):
    answer = ''
    for f in range(1, len(food)):
        answer += str(f) * (food[f]//2) 
    return answer + '0' + answer[::-1]
```

​     

### Day19

#### 체육복

```python
## Mine
def solution(n, lost, reserve):
    lost, reserve = set(lost)-set(reserve), set(reserve)-set(lost)
    for i in reserve:
        if i-1 in lost:
            lost.remove(i-1)
        elif i+1 in lost:
            lost.remove(i+1)
    return n-len(lost)
  
  
## Others
# lost를 기준으로
def solution(n, lost, reserve):
    lost, reserve = set(lost)-set(reserve), set(reserve)-set(lost)
    for i in lost:
        if i-1 in reserve:
            reserve.remove(i-1)
        elif i+1 in reserve:
            reserve.remove(i+1)
        else:  #위아래 번호에 여벌이 없으면 체육복 없음
            n -= 1
    return n
```

​     

### Day20

#### 완주하지 못한 선수

- [문제 설명]

  수많은 마라톤 선수들이 마라톤에 참여하였습니다. 단 한 명의 선수를 제외하고는 모든 선수가 마라톤을 완주하였습니다.

  마라톤에 참여한 선수들의 이름이 담긴 배열 participant와 완주한 선수들의 이름이 담긴 배열 completion이 주어질 때, 완주하지 못한 선수의 이름을 return 하도록 solution 함수를 작성해주세요.

- [제한 사항]

  - 마라톤 경기에 참여한 선수의 수는 1명 이상 100,000명 이하입니다.
  - completion의 길이는 participant의 길이보다 1 작습니다.
  - 참가자의 이름은 1개 이상 20개 이하의 알파벳 소문자로 이루어져 있습니다.
  - 참가자 중에는 동명이인이 있을 수 있습니다.

- [입출력 예]

  | participant                                       | completion                               | return   |
  | ------------------------------------------------- | ---------------------------------------- | -------- |
  | ["leo", "kiki", "eden"]                           | ["eden", "kiki"]                         | "leo"    |
  | ["marina", "josipa", "nikola", "vinko", "filipa"] | ["josipa", "filipa", "marina", "nikola"] | "vinko"  |
  | ["mislav", "stanko", "mislav", "ana"]             | ["stanko", "ana", "mislav"]              | "mislav" |

```python
## Mine
from collections import Counter
def solution(participant, completion):
    answer = Counter(participant) - Counter(completion)
    return list(answer.keys())[0]
  

## Others
# 정렬을 통해 일치하지 않는 요소 찾기
def solution(participant, completion):
    participant.sort()
    completion.sort()    
    for i in range(len(completion)):
        if participant[i] != completion[i]:
            return participant[i]
    return participant[-1]
  
# hash()
def solution(participant, completion):
    hash_dict, hash_sum = dict(), 0
    
    for part in participant:
        hash_dict[hash(person)] = person
        hash_sum += hash(person)
        
    for comp in completion:
        hash_sum -= hash(person)
        
    return hash_dict[hash_sum]
```

   

### Day21

#### 가장 가까운 글자(#해시 #연결리스트)

- [문제 설명]

  문자열 `s`가 주어졌을 때, `s`의 각 위치마다 자신보다 앞에 나왔으면서, 자신과 가장 가까운 곳에 있는 같은 글자가 어디 있는지 알고 싶습니다.예를 들어, `s`="banana"라고 할 때, 각 글자들을 왼쪽부터 오른쪽으로 읽어 나가면서 다음과 같이 진행할 수 있습니다.

  - b는 처음 나왔기 때문에 자신의 앞에 같은 글자가 없습니다. 이는 -1로 표현합니다.
  - a는 처음 나왔기 때문에 자신의 앞에 같은 글자가 없습니다. 이는 -1로 표현합니다.
  - n은 처음 나왔기 때문에 자신의 앞에 같은 글자가 없습니다. 이는 -1로 표현합니다.
  - a는 자신보다 두 칸 앞에 a가 있습니다. 이는 2로 표현합니다.
  - n도 자신보다 두 칸 앞에 n이 있습니다. 이는 2로 표현합니다.
  - a는 자신보다 두 칸, 네 칸 앞에 a가 있습니다. 이 중 가까운 것은 두 칸 앞이고, 이는 2로 표현합니다.

  따라서 최종 결과물은 [-1, -1, -1, 2, 2, 2]가 됩니다.

  문자열 `s`이 주어질 때, 위와 같이 정의된 연산을 수행하는 함수 solution을 완성해주세요.

- [제한 사항]

  - 1 ≤ s의 길이 ≤ 10,000
    - `s`은 영어 소문자로만 이루어져 있습니다.

- [입출력 예]

  | s        | result                  |
  | -------- | ----------------------- |
  | "banana" | [-1, -1, -1, 2, 2, 2]   |
  | "foobar" | [-1, -1, 1, -1, -1, -1] |

```python
## Mine
def solution(s):
    words = {}
    answer = []
    for i, c in enumerate(s):
        if c not in words:
            answer.append(-1)
        else:
            answer.append(i-words[c])
        words[c] = i
    return answer
# 중복된 문자열의 모든 인덱스를 담고 싶으면 if문은 words[c] = i, else문에는 words[c].append(i)
  
  
## Others
def solution(s):
    answer = []
    for i in range(len(s)):
        j = s.find(s[i])
        if i == j:
            answer.append(-1)
        else:
            answer.append(i-j)
            s = s.replace(s[j], ' ', 1)  #중복 문자의 인덱스를 찾기 위해 문자 삭제
    return answer
```



### Day22

#### 키패드 누르기

- [문제 설명]

  스마트폰 전화 키패드의 각 칸에 다음과 같이 숫자들이 적혀 있습니다.

  ![https://grepp-programmers.s3.ap-northeast-2.amazonaws.com/files/production/4b69a271-5f4a-4bf4-9ebf-6ebed5a02d8d/kakao_phone1.png](https://grepp-programmers.s3.ap-northeast-2.amazonaws.com/files/production/4b69a271-5f4a-4bf4-9ebf-6ebed5a02d8d/kakao_phone1.png)

  이 전화 키패드에서 왼손과 오른손의 엄지손가락만을 이용해서 숫자만을 입력하려고 합니다.맨 처음 왼손 엄지손가락은 `*` 키패드에 오른손 엄지손가락은 `#` 키패드 위치에서 시작하며, 엄지손가락을 사용하는 규칙은 다음과 같습니다.

  1. 엄지손가락은 상하좌우 4가지 방향으로만 이동할 수 있으며 키패드 이동 한 칸은 거리로 1에 해당합니다.
  2. 왼쪽 열의 3개의 숫자 `1`, `4`, `7`을 입력할 때는 왼손 엄지손가락을 사용합니다.
  3. 오른쪽 열의 3개의 숫자 `3`, `6`, `9`를 입력할 때는 오른손 엄지손가락을 사용합니다.
  4. 가운데 열의 4개의 숫자 `2`, `5`, `8`, `0`을 입력할 때는 두 엄지손가락의 현재 키패드의 위치에서 더 가까운 엄지손가락을 사용합니다.4-1. 만약 두 엄지손가락의 거리가 같다면, 오른손잡이는 오른손 엄지손가락, 왼손잡이는 왼손 엄지손가락을 사용합니다.

  순서대로 누를 번호가 담긴 배열 numbers, 왼손잡이인지 오른손잡이인 지를 나타내는 문자열 hand가 매개변수로 주어질 때, 각 번호를 누른 엄지손가락이 왼손인 지 오른손인 지를 나타내는 연속된 문자열 형태로 return 하도록 solution 함수를 완성해주세요.

- [제한 사항]

  - numbers 배열의 크기는 1 이상 1,000 이하입니다.
  - numbers 배열 원소의 값은 0 이상 9 이하인 정수입니다.
  - hand는 "left" 또는 "right" 입니다.
    - `"left"`는 왼손잡이, `"right"`는 오른손잡이를 의미합니다.
  - 왼손 엄지손가락을 사용한 경우는 `L`, 오른손 엄지손가락을 사용한 경우는 `R`을 순서대로 이어붙여 문자열 형태로 return 해주세요.

- [입출력 예]

  | numbers                           | hand    | result        |
  | --------------------------------- | ------- | ------------- |
  | [1, 3, 4, 5, 8, 2, 1, 4, 5, 9, 5] | "right" | "LRLLLRLLRRL" |
  | [7, 0, 8, 2, 8, 3, 1, 5, 7, 6, 2] | "left"  | "LRLLRRLLLRR" |
  | [1, 2, 3, 4, 5, 6, 7, 8, 9, 0]    | "right" | "LLRLLRLLRL"  |

```python
## Mine
def solution(numbers, hand):
    answer = ''
    left = 10
    right = 12
    for n in numbers:
        if n == 0:
            n = 11
        if n % 3 == 1:  #왼손라인
            answer += 'L'
            left = n
        elif n % 3 == 0:  #오른손라인
            answer += 'R'
            right = n
        else:  #중간라인
            Ldist = abs(n-left)//3 + abs(n-left)%3
            Rdist = abs(n-right)//3 + abs(n-right)%3
					
            if (Ldist < Rdist) or (Ldist == Rdist and hand == 'left'):  #왼손이 더 짧거나, 왼손잡이이고 거리가 동일할 때
                answer += 'L'
                left = n
            else:  #오른손이 더 짧거나 거리가 동일하고 오른손잡이일 때
                answer += 'R'
                right = n
    return answer
```



### Day23

#### 크레인 인형뽑기 게임(#스택)

- [문제 설명]

  게임개발자인 "죠르디"는 크레인 인형뽑기 기계를 모바일 게임으로 만들려고 합니다."죠르디"는 게임의 재미를 높이기 위해 화면 구성과 규칙을 다음과 같이 게임 로직에 반영하려고 합니다.

  ![https://grepp-programmers.s3.ap-northeast-2.amazonaws.com/files/production/69f1cd36-09f4-4435-8363-b71a650f7448/crane_game_101.png](https://grepp-programmers.s3.ap-northeast-2.amazonaws.com/files/production/69f1cd36-09f4-4435-8363-b71a650f7448/crane_game_101.png)

  게임 화면은 **"1 x 1"** 크기의 칸들로 이루어진 **"N x N"** 크기의 정사각 격자이며 위쪽에는 크레인이 있고 오른쪽에는 바구니가 있습니다. (위 그림은 "5 x 5" 크기의 예시입니다). 각 격자 칸에는 다양한 인형이 들어 있으며 인형이 없는 칸은 빈칸입니다. 모든 인형은 "1 x 1" 크기의 격자 한 칸을 차지하며 **격자의 가장 아래 칸부터 차곡차곡 쌓여 있습니다.** 게임 사용자는 크레인을 좌우로 움직여서 멈춘 위치에서 가장 위에 있는 인형을 집어 올릴 수 있습니다. 집어 올린 인형은 바구니에 쌓이게 되는 데, 이때 바구니의 가장 아래 칸부터 인형이 순서대로 쌓이게 됩니다. 다음 그림은 [1번, 5번, 3번] 위치에서 순서대로 인형을 집어 올려 바구니에 담은 모습입니다.

  ![https://grepp-programmers.s3.ap-northeast-2.amazonaws.com/files/production/638e2162-b1e4-4bbb-b0d7-62d31e97d75c/crane_game_102.png](https://grepp-programmers.s3.ap-northeast-2.amazonaws.com/files/production/638e2162-b1e4-4bbb-b0d7-62d31e97d75c/crane_game_102.png)

  만약 같은 모양의 인형 두 개가 바구니에 연속해서 쌓이게 되면 두 인형은 터뜨려지면서 바구니에서 사라지게 됩니다. 위 상태에서 이어서 [5번] 위치에서 인형을 집어 바구니에 쌓으면 같은 모양 인형 **두 개**가 없어집니다.

  ![https://grepp-programmers.s3.ap-northeast-2.amazonaws.com/files/production/8569d736-091e-4771-b2d3-7a6e95a20c22/crane_game_103.gif](https://grepp-programmers.s3.ap-northeast-2.amazonaws.com/files/production/8569d736-091e-4771-b2d3-7a6e95a20c22/crane_game_103.gif)

  크레인 작동 시 인형이 집어지지 않는 경우는 없으나 만약 인형이 없는 곳에서 크레인을 작동시키는 경우에는 아무런 일도 일어나지 않습니다. 또한 바구니는 모든 인형이 들어갈 수 있을 만큼 충분히 크다고 가정합니다. (그림에서는 화면표시 제약으로 5칸만으로 표현하였음)

  게임 화면의 격자의 상태가 담긴 2차원 배열 board와 인형을 집기 위해 크레인을 작동시킨 위치가 담긴 배열 moves가 매개변수로 주어질 때, 크레인을 모두 작동시킨 후 터트려져 사라진 인형의 개수를 return 하도록 solution 함수를 완성해주세요.

- [제한 사항]

  - board 배열은 2차원 배열로 크기는 "5 x 5" 이상 "30 x 30" 이하입니다.
  - board의 각 칸에는 0 이상 100 이하인 정수가 담겨있습니다.
    - 0은 빈 칸을 나타냅니다.
    - 1 ~ 100의 각 숫자는 각기 다른 인형의 모양을 의미하며 같은 숫자는 같은 모양의 인형을 나타냅니다.
  - moves 배열의 크기는 1 이상 1,000 이하입니다.
  - moves 배열 각 원소들의 값은 1 이상이며 board 배열의 가로 크기 이하인 자연수입니다.

- [입출력 예]

  | board                                                        | moves             | result |
  | ------------------------------------------------------------ | ----------------- | ------ |
  | [[0,0,0,0,0],[0,0,1,0,3],[0,2,5,0,1],[4,2,4,4,2],[3,5,1,3,1]] | [1,5,3,5,1,2,1,4] | 4      |

```python

```



### Day24

#### 과일 장수

- [문제 설명]

  과일 장수가 사과 상자를 포장하고 있습니다. 사과는 상태에 따라 1점부터 k점까지의 점수로 분류하며, k점이 최상품의 사과이고 1점이 최하품의 사과입니다. 사과 한 상자의 가격은 다음과 같이 결정됩니다.

  - 한 상자에 사과를 m개씩 담아 포장합니다.
  - 상자에 담긴 사과 중 가장 낮은 점수가 p (1 ≤ p ≤ k)점인 경우, 사과 한 상자의 가격은 p * m 입니다.

  과일 장수가 가능한 많은 사과를 팔았을 때, 얻을 수 있는 최대 이익을 계산하고자 합니다.(사과는 상자 단위로만 판매하며, 남는 사과는 버립니다)

  예를 들어, `k` = 3, `m` = 4, 사과 7개의 점수가 [1, 2, 3, 1, 2, 3, 1]이라면, 다음과 같이 [2, 3, 2, 3]으로 구성된 사과 상자 1개를 만들어 판매하여 최대 이익을 얻을 수 있습니다.

  - (최저 사과 점수) x (한 상자에 담긴 사과 개수) x (상자의 개수) = 2 x 4 x 1 = 8

  사과의 최대 점수 `k`, 한 상자에 들어가는 사과의 수 `m`, 사과들의 점수 `score`가 주어졌을 때, 과일 장수가 얻을 수 있는 최대 이익을 return하는 solution 함수를 완성해주세요.

- [제한 사항]

  - 3 ≤ `k` ≤ 9

  - 3 ≤ `m` ≤ 10

  - 7 ≤ 

    ```
    score
    ```

    의 길이 ≤ 1,000,000

    - 1 ≤ `score[i]` ≤ k

  - 이익이 발생하지 않는 경우에는 0을 return 해주세요.

- [입출력 예]

  | k    | m    | score                                | result |
  | ---- | ---- | ------------------------------------ | ------ |
  | 3    | 4    | [1, 2, 3, 1, 2, 3, 1]                | 8      |
  | 4    | 3    | [4, 1, 2, 2, 4, 4, 4, 4, 1, 2, 4, 2] | 33     |

```python
## Mine
def solution(k, m, score):
    answer = 0
    score.sort(reverse=True)
    for i in range(0, len(score), m):
        box = score[i:i+m]
        if len(box) == m:
            answer += len(box)*min(box)
    return answer
  
  
## Others
def solution(k, m, score):
    answer = 0
    score.sort(reverse=True)
    for i in range(len(score)//m):
        box = score[i*m:(i+1)*m]
        answer += min(box) * m
    return answer
  
  
# 박스별 최솟값만 골라서 계산하기
def solution(k, m, score):
    return sum(sorted(score)[len(score)%m::m])*m  #slicing[start:end:step]
```



### Day25

#### 숫자 짝꿍

- [문제 설명]

  두 정수 `X`, `Y`의 임의의 자리에서 공통으로 나타나는 정수 k(0 ≤ k ≤ 9)들을 이용하여 만들 수 있는 가장 큰 정수를 두 수의 짝꿍이라 합니다(단, 공통으로 나타나는 정수 중 서로 짝지을 수 있는 숫자만 사용합니다). `X`, `Y`의 짝꿍이 존재하지 않으면, 짝꿍은 -1입니다. `X`, `Y`의 짝꿍이 0으로만 구성되어 있다면, 짝꿍은 0입니다.

  예를 들어, `X` = 3403이고 `Y` = 13203이라면, `X`와 `Y`의 짝꿍은 `X`와 `Y`에서 공통으로 나타나는 3, 0, 3으로 만들 수 있는 가장 큰 정수인 330입니다. 다른 예시로 `X` = 5525이고 `Y` = 1255이면 `X`와 `Y`의 짝꿍은 `X`와 `Y`에서 공통으로 나타나는 2, 5, 5로 만들 수 있는 가장 큰 정수인 552입니다(`X`에는 5가 3개, `Y`에는 5가 2개 나타나므로 남는 5 한 개는 짝 지을 수 없습니다.)두 정수 `X`, `Y`가 주어졌을 때, `X`, `Y`의 짝꿍을 return하는 solution 함수를 완성해주세요.

- [제한 사항]

  - 3 ≤ `X`, `Y`의 길이(자릿수) ≤ 3,000,000입니다.
  - `X`, `Y`는 0으로 시작하지 않습니다.
  - `X`, `Y`의 짝꿍은 상당히 큰 정수일 수 있으므로, 문자열로 반환합니다.

- [입출력 예]

  | X       | Y        | result |
  | ------- | -------- | ------ |
  | "100"   | "2345"   | "-1"   |
  | "100"   | "203045" | "0"    |
  | "100"   | "123450" | "10"   |
  | "12321" | "42531"  | "321"  |
  | "5525"  | "1255"   | "552"  |

```python
## Mine
# 시간초과 문제 해결에 초점!
def solution(X, Y):
    answer = ''
    for n in range(9, -1, -1):  #sort를 사용하지 않고 내림차순 정렬 가능
        answer += str(n) * min(X.count(str(n)), Y.count(str(n)))

    if answer == '':
        return '-1'
    elif answer[0] == '0':  #int(answer)==0과 같은 형변환은 시간 초과
        return '0'
    return answer
  
  
## Others
# list.count() 활용 -> 가장 속도 빠름!
def solution(X, Y):
    x_lst = [X.count(str(x))for x in range(10)]
    y_lst = [Y.count(str(x))for x in range(10)]
    answer = ''
    for i in range(9, -1, -1):
        answer += str(i) * min(x_lst[i], y_lst[i])
        
    if answer == '': return '-1'
    if answer[0] == '0': return '0'
    return answer
  
# Counter 활용1
from collections import Counter
def solution(X, Y):
    X, Y = Counter(X), Counter(Y)
    answer = ''
    for i in range(9, -1, -1):
        if str(i) in X and str(i) in Y:
            answer += str(i)*min(X.get(str(i)), Y.get(str(i)))
    if answer == '': 
     	 return '-1'
    if answer[0] == '0': 
     	 return '0'
    return answer
  
# Counter 활용2
def solution(X, Y):
    X, Y = Counter(X), Counter(Y)
    answer = ''
    for i in range(9, -1, -1):
    		answer = ''.join([answer, str(i)*min(X[str(i)], Y[str(i)])])
    if answer == '': 
    		return "-1"
    elif len(answer) == answer.count('0'): 
    	  return '0'
    return answer
```

​    
