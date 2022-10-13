# Programmers 코딩 테스트 연습

   

## 코딩테스트 입문(Lv.0)

### Day1 사칙연산

- 두 수의 합

  ```python
  def solution(num1, num2):
      return num1 + num2
  ```

- 두 수의 차

  ```python
  def solution(num1, num2):
      return num1 - num2
  ```

- 두 수의 곱

  ```python
  def solution(num1, num2):
      return num1*num2
  ```

- 몫 구하기

  ```python
  def solution(num1, num2):
      return num1 // num2
  ```

  

### Day2 사칙연산, 조건문, 배열

- 두 수의 나눗셈

  ```python
  def solution(num1, num2):
      answer = int(num1/num2*1000)
      return answer
  ```

- 숫자 비교

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

  

- 분수의 덧셈

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

  

- 배열 두 배 만들기

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

  

