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


