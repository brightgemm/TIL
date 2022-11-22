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

​    

### Day9 수학, 문자열, 해시, 완전탐색, 조건문

#### 개미군단

```python
def solution(hp):
    return hp//5 + hp%5//3 + hp%5%3
```

#### 모스부호

```python
def solution(letter):
    morse = { 
    '.-':'a','-...':'b','-.-.':'c','-..':'d','.':'e','..-.':'f',
    '--.':'g','....':'h','..':'i','.---':'j','-.-':'k','.-..':'l',
    '--':'m','-.':'n','---':'o','.--.':'p','--.-':'q','.-.':'r',
    '...':'s','-':'t','..-':'u','...-':'v','.--':'w','-..-':'x',
    '-.--':'y','--..':'z'
    }
    answer = ''
    for char in letter.split():
        answer += morse.get(char)
    return answer

# join 활용하기
def solution(letter):
		morse = { ... }
    return ''.join([morse[i] for i in letter.split()])

```

#### 가위바위보

- [map()](https://www.w3schools.com/python/ref_func_map.asp)

```python
## Mine
def solution(rsp):
    rsp_dict = {'2': '0', '0': '5', '5': '2'}
    return ''.join([rsp_dict.get(x) for x in rsp])

## Others
# map과 lambda 함수 이용하기!
def solution(rsp):
  	return ''.join(map(lambda x : '5' if x=='0' else '0' if x=='2' else '2', rsp))

  
# map(function, iterables): map(함수 적용된 iterable객체)
# map함수 실행 시 map object로 반환되기 때문에 여러 개의 결과값을 한번에 보기 위해서는 list(map())과 같이 리스트화 시키는 것이 일반적!
# map 활용 예시
def myfunc(a, b):
  return a + b

x = map(myfunc, ('apple', 'banana', 'cherry'), ('orange', 'lemon', 'pineapple'))

print(x)
>>> <map object at 0x147397f3b2b0>

print(list(x))
>>> ['appleorange', 'bananalemon', 'cherrypineapple']
```

#### 구슬을 나누는 경우의 수

```python
## Mine
# for문을 이용하여 각각 팩토리얼 적용
def solution(balls, share):
    n, m, overlap = 1, 1, 1
    for i in range(balls, 1, -1):
        n *= i
    for i in range(balls-share, 1, -1):
        overlap *= i
    for i in range(share, 1, -1):
        m *= i
    return int(n/(overlap*m))

# math-factorial 함수 사용
def solution(balls, share):
	return f(balls)/(f(balls-share)*f(share))

# factorial 함수 정의
def factorial(num): 
    result = 1
    for i in range(num,1,-1):
        result *= i
    return result

def solution(balls, share):
    return factorial(balls)/(factorial(balls-share)*factorial(share))
  
## Others
# factorial 정의하는 방법2: 재귀함수 활용하기
def factorial(n):
  	return 1 if n==1 or n==0 else n*factorial(n-1)
  
# n!/(n-m)!*m! = (n-(n-m)(!/m!
# Ex. 5C3 = 5*4*3/3!
def solution(balls, share):
    denom, numer = 1, 1
    for i in range(balls, balls-share, -1):
        denom *= i
    for i in range(share, 1, -1):
        numer *= i
    return denom/numer
```

​     

### Day10 조건문, 배열, 수학, 시뮬레이션

#### 점의 위치 구하기

```python
def solution(dot):
    x, y = dot[0], dot[1]
    if x>0 and y>0:
        return 1
    elif x<0 and y>0:
        return 2
    elif x<0 and y<0:
        return 3
    else:
        return 4
```

#### 2차원으로 만들기

```python
def solution(num_list, n):
    answer = []
    for i in range(0, len(num_list), n):
        answer.append(num_list[i:i+n])
    return answer
```

#### 공 던지기

```python
def solution(numbers, k):
    return numbers[(k*2-2)%len(numbers)]
```

#### 배열 회전시키기

```python
# 방법1
def solution(numbers, direction):
    if direction == 'right':
        return [numbers.pop(-1)] + numbers
    else:
        return numbers + [numbers.pop(0)]

# 방법2
def solution(numbers, direction):
    return [numbers[-1]] + numbers[0:-1] if direction=='right' else numbers[1:] + [numbers[0]]
```

​    

### Day11 수학, 반복문

#### 주사위의 개수

```python
def solution(box, n):
    return (box[0]//n)*(box[1]//n)*(box[2]//n)
```

#### 합성수 찾기

```python
## Mine
def count_div(n):  # 1과 자기자신 외의 약수 개수 세기
    count = 0
    for i in range(2,n):
        if n%i == 0:
            count += 1
    return count

def solution(n):
    answer = 0
    for i in range(n+1):
        if count_div(i) >= 1:
            answer += 1
    return answer

## Others
def solution(n):
    answer = 0
    for num in range(4, n+1):  # 최소 합성수 4부터 n까지
        for i in range(2, int(num**0.5)+1):  # 2부터 n제곱근까지
            if num % i == 0:
                answer += 1
                break
    return answer
```

#### 최댓값 만들기(1)

```python
def solution(numbers):
    numbers = sorted(numbers)
    return numbers[-1] * numbers[-2]
```

#### 팩토리얼

```python
## Mine
def factorial(n):
    return 1 if n==0 or n==1 else n*factorial(n-1)

def solution(n):
    for i in range(1, 11):  # 문제 조건에서 n<= 10!이었으므로 최대 11까지
        if factorial(i) > n:
            max = i-1
            break
        elif factorial(i) == n:
            max = i
            break
        else:
            continue
    return max
  
## Others
# 방법1
def solution(n):
    for i in range(1, 12):
        if n//factorial(i) < 1:  # n보다 큰 팩토리얼이 되면
            return i-1
          
def factorial(n):
    return 1 if n==1 or n==0 else n*factorial(n-1)
  
# 방법2
def solution(n):
    cnt, k = 1, 1
    while cnt <= n:  # n보다 작은 최대 팩토리얼값 찾기. cnt=k!
        cnt *= k
        k += 1
    return k-2  # k+=1이 반복문 안에 있기 때문에 -2를 해줘야 최댓값 반환
```

​     

### Day12 문자열, 정렬, 사칙연산, 수학

#### 모음 제거하기

```python
## Mine
# 방법1
import re
def solution(my_string):
    return re.sub('[aeiou]','', my_string)

# 방법2
def solution(my_string):
    for char in 'aeiou':
        my_string = my_string.replace(char, '')
    return my_string
  

## Others
# list.remove()함수 사용
def solution(my_string):
  	my_string = list(my_string)
  	for vowel in my_string:
      	my_string.remove(vowel)
    return ''.join(my_string)
  
```

#### 문자열 정렬하기 (1)

- string 함수: `isdemical()` vs `isdigit()` vs `isnumeric()`
  - `isdigit()`: 단일 글자가 숫자 모양이면 `True`
  - `isdemical()`: int형으로 변환이 가능하면 `True` -> 숫자로 된 특수문자는 `False`
  - `isnumeric()`: 숫자값 표현에 해당하는 문자열까지 `True` ->	제곱근, 분수, 거듭제곱 `True`

```python
## Mine
import re
def solution(my_string):
    y_num = list(re.sub('[a-z]','',my_string))  #[^0-9]와 동일
    return sorted(list(map(int, my_num)))
  
  
##Others
# filter(function, iterable)+isdigit() 함수 이용
# isdemical() vs isdigit() vs isnumeric()
def solution(my_string):
  	# 숫자인 것만 필터링 -> int로 변환 -> 정렬
  	return sorted([int(k) for k in filter(lambda x: x.isdigit(), my_string)])
```

#### 숨어있는 숫자의 덧셈 (1)

```python
## Mine
import re
def solution(my_string):
    return sum(map(int, list(re.sub('[a-zA-Z]','',my_string))))

  
## Others
def solution(my_string):
  	return sum(int(k) for k in my_string if k.isdigit())
```

#### 소인수분해

```python
## Mine
def solution(n):
    k=2
    answer = []
    while k <= n
        if n%k == 0:
            n = n/k
            if k not in answer:
                answer.append(k)
        else:
            k += 1
    return answer

## Others
def solution(n):
    answer = []
    for i in range(2,n+1):  # 2이상의 약수를 가진 것
        while n%i == 0:
            n = n/i  # 2이상의 소수가 될 때까지 소인수분해
            if i not in answer:
                answer.append(i)
    return answer
```

​     

### Day13 문자열, 배열, 사칙연산, 수학, 조건문

#### 컨트롤 제트

```python
## Mine
def solution(s):
    s = s.split()
    for i in s:
        while 'Z' in s:  # Z가 없을 때까지 Z와 Z왼쪽 원소 제거하기
            s.pop(s.index('Z')-1)
            s.pop(s.index('Z'))
    return sum(map(int, s))
  

## Others
def solution(s):
    answer_list = []
    for i in s.split(' '):
        if i != 'Z':  # Z가 아니면 int로 변환하여 리스트에 추가
            answer_list.append(int(i))
        else:
            answer_list.pop()  # Z이면 가장 마지막 원소 pop하여 제거
    return sum(answer_list)
```

#### 배열 원소의 길이

```python
# 방법1
def solution(strlist):        
    answer = []
    for i in strlist:
        answer.append(len(i))
    return answer

# 한줄로!
def solution(strlist):        
    return [len(k) for k in strlist]
```

#### 중복된 문자 제거

```python
def solution(my_string):
    answer = ''
    for char in list(my_string):
        if char not in answer:
            answer += char
    return answer
```

#### 삼각형의 완성조건 (1)

```python
def solution(sides):
    sides = sorted(sides)  # sides.sort(reverse=Ture)와 동일
    return 1 if sides[0]+ sides[1]>sides[-1] else 2
```



### Day14 조건문, 반복문, 시뮬레이션, 문자열

#### 가까운 수

- [정렬 - sort(), sorted() + key](https://docs.python.org/ko/3/howto/sorting.html)
  - [`list.sort()`](https://docs.python.org/ko/3/library/stdtypes.html#list.sort)와 [`sorted()`](https://docs.python.org/ko/3/library/functions.html#sorted)는 각 리스트 요소에 대해 호출할 함수를 지정하는 *key* 매개 변수를 가짐
  - *key* 매개 변수의 값은 단일 인자를 취하고 정렬 목적으로 사용할 키를 반환하는 함수여야 함
- key함수와 operator 모듈 함수
  - operator 모듈의 `itemgetter()`, `attrgetter()` 및 `methodicaller()`와 결합하여 사용하면 더 간단하고 빠르게 작동함

```python
## Mine
def solution(array, n):
    diff_list = [array[0], abs(n-array[0])]
    for i in array:
        diff = abs(n-i)
        if diff < diff_list[1]:
            diff_list = [i, diff]
        elif i < diff_list[0] and diff == diff_list[1]:
            diff_list = [i, diff]
    return diff_list[0]
  

## Others
# sorted()의 key 파라미터를 활용
def solution(array, n):
    array.sort()
    return sorted(array, key = lambda x: abs(x-n))[0]
  
# key를 활용한 대소문자를 구분하지 않는 문자열 비교
sorted("This is a test string from Andrew".split(), key=str.lower)
>>> ['a', 'Andrew', 'from', 'is', 'string', 'test', 'This']

# key를 활용한 복잡한 객체 정렬
student_tuples = [('john', 'A', 15), ('jane', 'B', 12), ('dave', 'B', 10)]
sorted(student_tuples, key=lambda student: student[2])   # sort by age
>>> [('dave', 'B', 10), ('jane', 'B', 12), ('john', 'A', 15)]

# key 함수 + operator 모듈
from operator import itemgetter, attrgetter

sorted(student_tuples, key=itemgetter(2))  # 2번째 인덱스를 기준으로 정렬
>>> [('dave', 'B', 10), ('jane', 'B', 12), ('john', 'A', 15)]

sorted(student_objects, key=attrgetter('grade', 'age'))  # grade로 정렬 후 age로 정렬
>>> [('john', 'A', 15), ('dave', 'B', 10), ('jane', 'B', 12)]

```

#### 369게임

```python
def solution(order):
    count = 0
    for i in str(order):
        if i=='3' or i=='6'or i=='9':  # if i in '369'
            count += 1
    return count
```

#### 암호 해독

```python
def solution(cipher, code):
    answer = ''
    for i in range(code-1, len(cipher), code):
        answer += cipher[i]
    return answer
  
# 한줄로~
def solution(cipher, code):
  	return ''.join([cipher[k] for k in range(code-1, len(cipher), code)])
```

#### 대문자와 소문자

```python
def solution(my_string):
    answer = ''
    for char in my_string:
        if char.isupper():
            answer += char.lower()
        else:
            answer += char.upper()
    return answer
```

   

### Day15 문자열, 해시, 배열, 수학

#### 영어가 싫어요

```python
def solution(numbers):
    num_dict = {'zero': 0, 'one': 1, 'two': 2, 'three': 3, 'four': 4,
                'five': 5, 'six': 6, 'seven': 7, 'eight': 8, 'nine': 9}
    for num in num_dict:
        if num in numbers:
            numbers = numbers.replace(num, str(num_dict.get(num)))
    return int(numbers)

  
# 딕셔너리를 모두 문자열로 저장 후 replace 사용
def solution(numbers):
    num_dict = {'zero':'0', 'one':'1', 'two':'2', 'three':'3', 'four':'4', 
                'five':'5', 'six':'6', 'seven':'7', 'eight':'8', 'nine':'9'}
    for num in num_dict.keys():
        numbers = numbers.replace(num, num_dict[num])
    return int(numbers)
```

#### 인덱스 바꾸기

```python
def solution(my_string, num1, num2):
    my_string = list(my_string)
    my_string[num1], my_string[num2] = my_string[num2], my_string[num1]
    return ''.join(my_string)
```

#### 한 번만 등장한 문자

```python
## Mine
def solution(s):
    answer = ''
    s_list = sorted(list(s))
    for char in s_list:
        if s_list.count(char) == 1:
            answer += char
    return answer
  
  
## Others
def solution(s):
  return ''.join(sorted(filter(lambda x: s.count(x) == 1, s))) # filter + lambda
	return ''.join(sorted([k for k in s if s.count(k) == 1])) # 리스트내포
```

#### 약수 구하기

```python
## Mine
def solution(n):
    answer = []
    for i in range(1, n//2+1): # n의 절반까지 쌍으로 추가하기
        if n%i == 0:
            answer.append(i)
            answer.append(n/i)
    return sorted(list(set(answer)))
  
  
## Others
def solution(n): 
  	return [k for k in range(1, n+1) if n%k == 0] # n까지 약수 모두 추가
```

​    

### Day16 문자열, 수학, 배열, 조건문

#### 편지

```python
def solution(message):
    return len(message)*2
```

#### 가장 큰 수 찾기

```python
def solution(array):
    return [max(array), array.index(max(array))]
```

#### 문자열 계산하기

```python
# 방법1 eval()
def solution(my_string):
    return eval(my_string)

# 방법2 문자별로 자료형 변경하기
def solution(my_string):
		s = my_string.split()
		answer = int(s[0])
		for i in range(1, len(s), 2):
		    if s[i] == '+':
		        answer += int(s[i+1])
		    if s[i] == '-':
		        answer -= int(s[i+1])
		return answer
```

#### 배열의 유사도

```python
## Mine
def solution(s1, s2):
    return len([k for k in s1 if k in s2])
  
  
## Others
# 교집합 이용하기
def solution(s1, s2):
  	return len(set(s1)&set(s2))
```

​    

### Day17 문자열, 수학, 조건문, 배열, 사칙연산

#### 숫자 찾기

```python
## Mine
def solution(num, k):
    loc = str(num).find(str(k))
    return loc if loc == -1 else loc+1
  
  
## Others
def solution(num, k):
  	return (lambda x: x+1 if x>=0 else x)(str(num).find(str(k)))  #lambda함수의 매개변수로 str().find() 결과값을 지정
```

#### n의 배수 고르기

```python
def solution(n, numlist):
    return [k for k in numlist if k%n==0]  #리스트내포
 		return list(filter(lambda x: x%n==0, numlist))  #filter+lambda
```

#### 자릿수 더하기

```python
def solution(n):
    return sum(map(int, str(n))) 
  	return sum([int(k) for k in str(n)])
```

#### OX퀴즈

```python
## Mine
# 방법1
def solution(quiz):
    answer = []
    for q in quiz:
        if eval(q.split('=')[0]) == eval(q.split('=')[1]):
            answer.append("O")
        else:
            answer.append("X")
    return answer

# 방법2
def solution(quiz):
    answer = []
    q = [x.replace('=', '==') for x in quiz]  #eval로 인식할 수 있도록 ==으로 변경
    for x in q:
        if eval(x) == True:
            answer.append("O")
        else:
            answer.append("X")
    return answer
  
  
## Others
# lambda 활용
def solution(quiz):
  	quiz = list(map(lambda x: x.split(' = '), quiz))  #[식, 답] 형태로 분리
    answer = list(map(lambda x: 'O' if eval(x[0])==eval(x[1]) else 'X', quiz))
    return answer
    
    
## lambda를 활용하여 방법2를 이렇게 수정하자!
def solution(quiz):
  	q = [k.replace('=', '==') for k in quiz]
    return list(map(lambda x: 'O' if eval(x) else 'X', q))
```

​    

### Day18 문자열, 수학, 조건문, 정렬

#### 문자열안에 문자열

```python
def solution(str1, str2):
    return 2 if str1.find(str2)== -1 else 1
  	return 1 if str2 in str1 else 2
```

#### 제곱수 판별하기

```python
## Mine
def solution(n):
    answer = [k for k in range(n) if k*k == n]
    return 1 if len(answer) == 1 else 2
  
  
## Others
def solution(n):
  	return 1 if n**0.5 == int(n**0.5) else 2  # '**'제곱을 활용하여 제곱근 취하기
  	return 1 if (n**0.5).is_integer() else 2  # is_integer() 함수를 통해 정수 여부 판별
```

#### 세균 증식

```python
# 방법1
def solution(n, t):
    for i in range(1, t+1):
        n *= 2
    return n

# 방법2
def solution(n, t):
  	return n*(2**t)
```

#### 문자열 정렬하기(2)

```python
def solution(my_string):
    return ''.join(sorted(my_string.lower()))
```

​    

### Day19 문자열, 배열, 조건문

#### 7의 개수

```python
def solution(array):
    return str(array).count('7')
```

#### 잘라서 배열로 저장하기

```python
def solution(my_str, n):
    answer = []
    for i in range(0, len(my_str), n):
        answer.append(my_str[i:i+n])
    return answer
```

#### 중복된 숫자 개수

```python
def solution(array, n):
    return array.count(n)
```

#### 머쓱이보다 키 큰 사람

```python
## Mine
def solution(array, height):
    answer = 0
    for i in array:
        if height < i:
            answer += 1
    return answer
  
  
## Others
def solution(array, height):
  	return sum([1 for k in array if k>height])  #키 큰 사람 수만큼 1 더하기
  	return len(list(filter(lambda x: x > height, array)))  #키 큰 사람 필터링 후 원소 개수
  
def solution(array, height):
  	array.append(height)  #배열에 비교대상을 추가해서 
    array.sort()  #정렬 후 
    return array.index(height)  #비교대상의 인덱스 번호 출력하기
```

​    

### Day20 수학, 시뮬레이션, 문자열, 사칙연산

#### 직사각형 넓이 구하기

```python
# 방법1
def solution(dots):
    return abs(max(dots)[1]-min(dots)[1])*abs(max(dots)[0]-min(dots)[0])
  
# 방법2
def solution(dots):
		dots.sort()
    return abs((dots[0][1]-dots[1][1])*(dots[0][0]-dots[3][0]))
```

#### 캐릭터의 좌표

```python
## Mine
def solution(keyinput, board):
    answer = [0, 0]
    for direction in keyinput:
        if direction == 'left' and -(board[0]//2) <  answer[0]:
            answer[0] -= 1
        elif direction == 'right' and board[0]//2 > answer[0]:
            answer[0] += 1
        elif direction == 'up' and board[1]//2 > answer[1]:
            answer[1] += 1
        elif direction == 'down' and -(board[1]//2) < answer[1]:
            answer[1] -= 1
    return answer
```

#### 최댓값 만들기(2)

```python
def solution(numbers):
    numbers = sorted(numbers)
    return max(numbers[0]*numbers[1], numbers[-1]*numbers[-2])
```

#### 다항식 더하기

```python
## Mine
def solution(polynomial):
    x_list = []
    for k in polynomial.split():
        if k == 'x':
            x_list.append(k.replace('x', '1'))
        elif 'x' in k:
            x_list.append(k.replace('x', ''))
            
    x_list = list(map(int, x_list))
    num_list = [int(k) for k in polynomial.split() if k.isdigit()]
    answer = [sum(x_list), sum(num_list)]
    
    if answer[0] == 1:  #x계수가 1일 때
        if answer[1] == 0:
            return 'x'
        else:
            return f'x + {answer[1]}'
    elif answer[0] == 0:  #상수항 있을 때
        return f'{answer[1]}'
    elif answer[1] == 0:  #X항만 있을 때
        return f'{answer[0]}x'
    else:
        return f'{answer[0]}x + {answer[1]}'
      
      
## Others
def solution(polynomial):
    x_num, num = 0, 0
    for pol in polynomial.split(' + '):
        if 'x' in pol:  #x항 계산
            if pol == 'x': pol = 1
            else: pol = int(pol.replace('x', ''))
            x_num += int(pol)
                      
        else:  #상수항 계산
            num += int(pol)
            
    answer = []
    if x_num != 0:
        answer.append('x' if x_num == 1 else f'{x_num}x')
    if num != 0:
        answer.append(f'{num}')

    return ' + '.join(answer)  #x항과 상수항 둘 다 0이 아닐 때 + 로 연결

```

​     

### Day 21 문자열, 사칙연산, 시뮬레이션, 2차원배열, 수학, 배열

#### 숨어있는 숫자의 덧셈(2)

- [re 정규식 연산](https://docs.python.org/ko/3/library/re.html)

```python
## Mine
import re

def solution(my_string):
    my_string = re.sub('[^0-9]', " ", my_string)
    answer = 0
    for num in my_string.split():
        if num.isdigit():
            answer += eval(num)
    return answer
  

## Others
def solution(my_string):
    num_list = re.findall(r'\d+', my_string)  #\d : str에서 숫자를 의미
    return sum(map(int, num_list))
```

#### 안전지대

```python
def solution(board):
    for row in range(len(board)):
        for col in range(len(board)):
            if board[row][col] == 1:
              	#list out of range 방지(0보다 작을 땐 0, 리스트 길이보다 클 땐 리스트 길이 선택)
                for i in range(max(row-1,0), min(row+2, len(board))):  
                    for j in range(max(col-1, 0), min(col+2, len(board))):
                        if board[i][j] == 1
                        		: continue
                        board[i][j] = 2  #1이 아닌 임의의 숫자로 위험지대 표시
                        
    return sum(board[k].count(0) for k in range(len(board)))
```

#### 삼각형의 완성조건(2)

```python
## Mine
def solution(sides):
    sides = sorted(sides)
    line_list = [k for k in range(sides[1]-sides[0]+1, sum(sides))]
    return len(line_list)
  
  
## Others
# 가장 긴 변이 나머지 합보다 작아야 함
def solution(sides):
  	return sum(sides) - max(sides) + min(sides) - 1
  	return min(sides)*2-1

```

#### 외계어 사전

```python
## Mine
def solution(spell, dic):
    answer = 2
    for i in dic:
        if set(spell) == set(i):
            answer -= 1
    return answer
```

