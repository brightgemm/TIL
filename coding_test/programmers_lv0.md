# Programmers 코딩 테스트 연습

   

## 코딩테스트 입문(Lv.0)

### Day1 사칙연산

#### 두 수의 합

```python
def solution(num1, num2):
    return num1 + num2
```

#### 두 수의 차

```python
def solution(num1, num2):
    return num1 - num2
```

#### 두 수의 곱

```python
def solution(num1, num2):
    return num1*num2
```

#### 몫 구하기

```python
def solution(num1, num2):
    return num1 // num2
```



### Day2 사칙연산, 조건문, 배열

#### 두 수의 나눗셈

```python
def solution(num1, num2):
    answer = int(num1/num2*1000)
    return answer
```

#### 숫자 비교

```python
## Mine
def solution(num1, num2):
    if num1 == num2:
        answer = 1
    else:
        answer = -1
    return answerr
 
# Others
# 간단한 if 문은 한 줄로 작성할 수 있다!(리스트내포 같이 작성)
def solution(num1, num2):
    return 1 if num1 == num2 else -1
```

#### 분수의 덧셈

```python
## Mine
def solution(denum1, num1, denum2, num2):
    denum = (denum1*num2) + (denum2*num1)
    num = num1*num2
    
    # 분모, 분자의 최대공약수로 약분
    for i in range(min(denum, num), 0, -1):
        if denum % i == 0 and num % i == 0:
            denum = denum / i
            num = num / i
            answer = [denum, num]
            break
    return answer

## Others
# 가장 작은 짝수인 2로 덧셈한 분수 먼저 나눠서 약분하기
# 주어진 숫자 범위인 1000까지 홀수의 약분 가능 여부 판단하여 약분하기
def solution(denum1, num1, denum2, num2):
    num3 = num1 * num2
    denum3 = denum1 * num2 + denum2 * num1
    while denum3 % 2 == 0 and num3 % 2 == 0:
        denum3 /= 2
        num3 /= 2
    for i in range(3, 1000, 2):
        while denum3 % i == 0 and num3 % i == 0:
            denum3 /= i
            num3 /= i
    return [denum3, num3]
  

# 2부터 분모의 곱+1까지 모두 체크하며 최대 공약수 찾기
def solution(denum1, num1, denum2, num2):
    denum = denum1 * num2 + denum2 * num1
    num = num1 * num2
    max = 1
    for i in range(2, num+1):
        if denum % i == 0 and num % i == 0:
            max = i
            
    denum = denum / max
    num = num / max
    answer = [denum, num]
    return answer

# 최대공약수로 약분하기 for & while문 활용
# while문을 활용하면 break를 따로 하지 않아도 됨!
for i in range(2, min(denum, num)+1):
    while (denum % i == 0) & (num % i == 0):
        denum = denum / i
        num = num / i

# math 라이브러리를 이용한 풀이
from math import gcd
def solution(denum1, num1, denum2, num2):
    denum = denum1*num2 + denum2*num1
    num = num1*num2
    gcd_num = gcd(denum, num)
    denum = denum/gcd_num
    num = num/gcd_num
    return [denum, num]

# 유클리드 호제법을 이용한 최대공약수 구하기
# a, b의 최대공약수 = a%b와 b의 최대공약수와 동일하다는 원리를 이용!
def gcd(a, b):
  while b > 0:
    a, b = b, a%b
    return a

# 번외) 최소공배수 구하기
# 최소공배수 = a*b를 최대공약수로 나눈 수
def lcm(a, b):
		return a*b/gcd(a, b)
```



#### 배열 두 배 만들기

```python
## Mine
def solution(numbers):
    return [x*2 for x in numbers]

  
## Others
# lambda 함수로 곱셈 정의 -> map 함수로 배열에 적용 -> list화(배열화)
def solution(numbers):
    return list(map(lambda x : 2*x, numbers))

# for문을 사용하여 원소별로 곱셈하여 리스트에 추가하는 방법
def solution(numbers):
    answer = []
    for num in numbers: # numbers는 iterable
    		answer.append(num*2)
    return answer
```



### Day3 사칙연산, 배열, 수학

#### 나머지 구하기

```python
def solution(num1, num2):
    return num1 % num2
```

#### 중앙값 구하기

```python
def solution(array):
    array = sorted(array)
    median = int(len(array)/2)
    return array[median]
```

#### 최빈값 구하기

```python
## Mine
def solution(array):
    answer = 0
    count_dict = {}
    for n in set(array):
        count_dict[n] = array.count(n)
		
    # 빈도수 최댓값 구하기
    max_count = max(list(count_dict.values()))
    
    # 최빈값의 key값 가져오기
    max_key = [k for k, v in count_dict.items() if v == max_count] 
    
		if len(max_key) > 1: # 최빈값 여러 개일 때
        return -1
    else:
		    return max_key[0] # 최빈값이 한 개일 때
```

#### 짝수는 싫어요

```python
def solution(n):
    answer = []
    for i in range(n+1):
        if i%2 != 0:
            answer.append(i)
    return answer
  
# 더 간단한 코드(리스트내포)
def solution(n):
  return [x for x in range(n+1) if x%2 != 0]
```

  

### Day4 수학, 배열

#### 피자 나눠 먹기(1)

```python
def solution(n):
  	if n%7 == 0:
      	answer = n//7
   	else:
      	answer = n//7 + 1
		return answer

# 더 간단한 코드
def solution(n):
  return n//7 if n%7 == 0 else n//7+1
```

#### 피자 나눠 먹기(2)

```python
## Mine
def solution(n):
  	pizza = 1
    while (pizza*6)%n != 0:
      	pizza += 1
    return pizza
  
## Others
# 유클리드 호제법 활용하기!
def solution(n):
    def gcd(a, b):
        while b>0:
            a, b = b, a%b
        return a
    return n//gcd(n, 6)
```

#### 피자 나눠 먹기(3)

```python
def solution(slice, n):
    return n//slice if n%slice == 0 else n//slice + 1
```

#### 배열의 평균값

```python
# 영롱
def solution(numbers):
    return sum(numbers)/len(numbers)
```



### Day5 수학, 배열

#### 옷가게 할인 받기

```python
def solution(price):
    if price >= 500000:
        price = int(price*0.8)
    elif 300000<= price < 500000:
        price = int(price*0.9)
    elif price >= 100000:
        price = int(price*0.95)
    return price
```

#### 아이스 아메리카노

```python
def solution(money):
    num = money//5500
    change = money%5500
    return [num, change]
```

#### 나이 출력

```python
def solution(age):
    return 2022-age+1
```

#### 배열 뒤집기

- [Extended Slices](https://docs.python.org/release/2.3.5/whatsnew/section-slices.html)

```python
## Mine
def solution(num_list):
    num_list.reverse()
    return num_list
  
## Others
# array[::] 슬라이싱 용법 활용하기!
# arr[a:b:c] = 인덱스 a부터 b까지 c 간격으로
def solution(num_list):
  return num_list[::-1]

## Extended Slices 활용 예시
arr = [1,2,3,4,5]
arr[::-1]  # 처음부터 끝까지 -1간격
>>> [5,4,3,2,1]
arr[3:5:-1]  # 인덱스 3부터 5미만까지 -1간격
>>> [4,5]
```

​    

### Day6 문자열, 반복문, 출력, 배열, 조건문

#### 문자열 뒤집기

```python
# extended slices 활용
def solution(my_string):
    return my_string[::-1]

# 반복문을 사용하여 빈 문자열에 덧붙이기
def solution(my_string):
    r_string = ''
    for char in my_string:
        r_string = char + r_string
    return r_string
  
# reversed() -> 문자열에도 사용 가능!
def solution(my_string):
    my_string = ''.join(reversed(my_string))
    return my_string

# string.join(iterable)
# string method - join() 활용예시
myList = ['John', 'Peter', 'Vicky']
x = 'and'.join(myList)
print(x)
>>> JohnandPeterandVicky

```

#### 직각삼각형 출력하기

```python
n = int(input())
for i in range(1, n+1):
    print('*'*i)   # end="\n" 생략된 형태
```

#### 짝수 홀수 개수

```python
## Mine
def solution(num_list):
    even = [k for k in num_list if k%2==0]
    odd = [k for k in num_list if k%2!=0]
    return [len(even), len(odd)]
  
## Others
# for문을 통해 개수를 카운팅하기
def solution(num_list):
		even, odd = 0, 0
    for num in num_list:
      	if num%2 == 0:
          	even += 1
        else:
          	odd += 1
		return [even, odd]
```

#### 문자 반복 출력하기

```python
## Mine
def solution(my_string, n):
    answer = ''
    for char in my_string:
        answer += char*n
    return answer

## Others
# join 함수 + 리스트내포
def solution(my_string, n):
		return ''.join([x*n for x in my_string])  
```

​    

### Day7 문자열, 조건문, 수학, 반복문

#### 특정 문자 제거하기

```python
def solution(my_string, letter):
    answer = my_string.replace(letter,'')
    return answer
```

#### 각도기

```python
def solution(angle):
    if angle < 90: 
        return 1
    elif angle == 90: 
        return 2
    elif 90 < angle < 180:
        return 3
    else:
        return 4
```

#### 양꼬치

```python
def solution(n, k):
    return 12000*n + 2000*(k-n//10)
```

#### 짝수의 합

```python
## Mine
def solution(n):
    answer = 0
    for i in range(n+1):
        if i%2 == 0:
            answer += i
    return answer

## Others
def solution(n):
  return sum([k for k in range(2, n+1, 2)])
```

​    

### Day8 배열, 구현, 수학

#### 배열 자르기

```python
def solution(numbers, num1, num2):
    return numbers[num1:num2+1]
```

#### 외계행성의 나이

```python
## Mine
def solution(age):
    char = 'abcdefghij'
    age = list(str(age))
    answer=''
    for i in range(len(age)):
        answer += char[int(age[i])]
    return answer

## Others
# join 활용 + string은 iterable!, callable!
def solution(age):
  char = 'abcdefghij'
  return ''.join([char[int(i)] for i in str(age)])
```

#### 진료 순서 정하기

```python
## Mine
def solution(emergency):
    sort_list = sorted(emergency, reverse=True)  #내림차순 정렬
    my_dict = {}
    my_turn = []
    for i, e in enumerate(sort_list)  #{내림차순: 순서} 생성
        my_dict[e]=i+1
    for num in emergency:
        my_turn.append(my_dict.get(num))  #원본 숫자를 key로 갖는 value 호출하여 리스트에 추가
    return my_turn
  
## Others
# 리스트의 인덱스 활용하기
def solution(emergency):
    sort_em = sorted(emergency, reverse=True)
    return [sort_em.index(i)+1 for i in emergency]
```

#### 순서쌍의 개수

```python
def solution(n):
    # 약수의 개수
    num_list = [k for k in range(1, n+1) if n%k==0]
    return len(num_list)
  
## Others
def solution(n):
  	# 제곱수인 경우는 개수-1 (앞뒤 순서 바뀐 경우가 없음!)
    answer = -1 if n**0.5 == int(n**0.5) else 0
    for i in range(1, int(n**0.5) + 1):  #1~순서쌍 절반까지만 확인
        if n%i == 0:
            answer += 2  #순서쌍이므로 2개씩 추가하기
    return answer
```

