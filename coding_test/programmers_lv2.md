# Programmers 코딩 테스트 연습



## 코딩테스트(Lv.2)

> 모든문제>안 푼 문제>난이도2>Python3>정답률 높은 순 정렬

   

### Day1

#### 최댓값과 최솟값

- [문제 설명]

  - 문자열 s에는 공백으로 구분된 숫자들이 저장되어 있습니다. str에 나타나는 숫자 중 최소값과 최대값을 찾아 이를 "(최소값) (최대값)"형태의 문자열을 반환하는 함수, solution을 완성하세요.
    예를들어 s가 "1 2 3 4"라면 "1 4"를 리턴하고, "-1 -2 -3 -4"라면 "-4 -1"을 리턴하면 됩니다.

- [제한 조건]

  - s에는 둘 이상의 정수가 공백으로 구분되어 있습니다.

- [입출력 예]

  | s             | return  |
  | ------------- | :-----: |
  | "1 2 3 4"     |  "1 4"  |
  | "-1 -2 -3 -4" | "-4 -1" |
  | "-1 -1"       | "-1 -1" |

- [문제 풀이]

  ```python
  ## Mine
  def solution(s):
      s = [int(k) for k in s.split()]
      # s = list(map(int, s.split()))
      
      return ' '.join([str(min(s)), str(max(s))])
  ```

  

### Day2

#### JadenCase 문자열 만들기

- [문제 설명]

  JadenCase란 모든 단어의 첫 문자가 대문자이고, 그 외의 알파벳은 소문자인 문자열입니다. 단, 첫 문자가 알파벳이 아닐 때에는 이어지는 알파벳은 소문자로 쓰면 됩니다. (첫 번째 입출력 예 참고)

  문자열 s가 주어졌을 때, s를 JadenCase로 바꾼 문자열을 리턴하는 함수, solution을 완성해주세요.

- [제한 사항]

  - s는 길이 1 이상 200 이하인 문자열입니다.
  - s는 알파벳과 숫자, 공백문자(" ")로 이루어져 있습니다.
    - 숫자는 단어의 첫 문자로만 나옵니다.
    - 숫자로만 이루어진 단어는 없습니다.
    - 공백문자가 연속해서 나올 수 있습니다.

- [입출력 예]

  | s                       | return                  |
  | ----------------------- | ----------------------- |
  | "3people unFollowed me" | "3people Unfollowed Me" |
  | "for the last week"     | "For The Last Week"     |

- [문제 풀이]

  ```python
  ## Mine
  # 방법1: upper(), lower()
  def solution(s):
      s = [word[0].upper() + word[1:].lower() for word in s.split(' ')]
      return ' '.join(s)
  
  # 방법2: capitalize()
  def solution(s):
      return ' '.join([word.capitalize() for word in s.split(' ')])
  ```

  

### Day3

#### 최솟값 만들기

- [문제 설명]

  길이가 같은 배열 A, B 두개가 있습니다. 각 배열은 자연수로 이루어져 있습니다.배열 A, B에서 각각 한 개의 숫자를 뽑아 두 수를 곱합니다. 이러한 과정을 배열의 길이만큼 반복하며, 두 수를 곱한 값을 누적하여 더합니다. 이때 최종적으로 누적된 값이 최소가 되도록 만드는 것이 목표입니다. (단, 각 배열에서 k번째 숫자를 뽑았다면 다음에 k번째 숫자는 다시 뽑을 수 없습니다.)

  예를 들어 A = `[1, 4, 2]` , B = `[5, 4, 4]` 라면

  - A에서 첫번째 숫자인 1, B에서 첫번째 숫자인 5를 뽑아 곱하여 더합니다. (누적된 값 : 0 + 5(1x5) = 5)
  - A에서 두번째 숫자인 4, B에서 세번째 숫자인 4를 뽑아 곱하여 더합니다. (누적된 값 : 5 + 16(4x4) = 21)
  - A에서 세번째 숫자인 2, B에서 두번째 숫자인 4를 뽑아 곱하여 더합니다. (누적된 값 : 21 + 8(2x4) = 29)

  즉, 이 경우가 최소가 되므로 **29**를 return 합니다.

  배열 A, B가 주어질 때 최종적으로 누적된 최솟값을 return 하는 solution 함수를 완성해 주세요.

- [제한 사항]

  - 배열 A, B의 크기 : 1,000 이하의 자연수
  - 배열 A, B의 원소의 크기 : 1,000 이하의 자연수

- [입출력 예]

  | A         | B         | answer |
  | --------- | --------- | ------ |
  | [1, 4, 2] | [5, 4, 4] | 29     |
  | [1,2]     | [3,4]     | 10     |

- [문제 풀이]

  ```python
  ## Mine
  def solution(A,B):
      answer = 0
      A, B = sorted(A), sorted(B, reverse=True)
      for i in range(len(A)):  #sum([A[i]*B[i] for i in range(len(A))])도 가능
          answer += A[i]*B[i]
      return answer
    
  ## Others
  # zip()
  def solution(A,B):
      return sum([x[0] * x[1] for x in zip(sorted(A), sorted(B, reverse=True))])
    	# return sum(a*b for a, b in zip(sorted(A), sorted(B, reverse=True)))
  ```



### Day4

#### 올바른 괄호

- [문제설명]

  괄호가 바르게 짝지어졌다는 것은 '(' 문자로 열렸으면 반드시 짝지어서 ')' 문자로 닫혀야 한다는 뜻입니다. 예를 들어

  - "()()" 또는 "(())()" 는 올바른 괄호입니다.

  - ")()(" 또는 "(()(" 는 올바르지 않은 괄호입니다.

  '(' 또는 ')' 로만 이루어진 문자열 s가 주어졌을 때, 문자열 s가 올바른 괄호이면 true를 return 하고, 올바르지 않은 괄호이면 false를 return 하는 solution 함수를 완성해 주세요.

- [제한사항]

  - 문자열 s의 길이 : 100,000 이하의 자연수

  - 문자열 s는 '(' 또는 ')' 로만 이루어져 있습니다.

- [입출력 예]

  | s          | answer |
  | ---------- | ------ |
  | "()()"     | true   |
  | "(())()"   | true   |
  | ")()("     | false  |
  | "(()("     | false  |
  | "()())(()" | false  |

- [문제 풀이]

  ```python
  ## Mine
  def solution(s):
      s = s.replace('()', '')
      if len(s) > 0:
          if s[0] == ')' or s[-1] == '(' or s.count('(') != s.count(')'):
              return False
      return True
    
    
  ## Others  
  def solution(s):
      count = 0
      for i in s:
          count += 1 if i == '(' else -1
          if count < 0:
              return False
      return count == 0
  ```




### Day5

#### 이진 변환 반복하기

- [문제 설명]
  
    0과 1로 이루어진 어떤 문자열 x에 대한 이진 변환을 다음과 같이 정의합니다.
    
    1. x의 모든 0을 제거합니다.
    2. x의 길이를 c라고 하면, x를 "c를 2진법으로 표현한 문자열"로 바꿉니다.
    
    예를 들어, `x = "0111010"`이라면, x에 이진 변환을 가하면 `x = "0111010" -> "1111" -> "100"` 이 됩니다.
    
    0과 1로 이루어진 문자열 s가 매개변수로 주어집니다. s가 "1"이 될 때까지 계속해서 s에 이진 변환을 가했을 때, 이진 변환의 횟수와 변환 과정에서 제거된 모든 0의 개수를 각각 배열에 담아 return 하도록 solution 함수를 완성해주세요.
    
- [제한 사항]
    - s의 길이는 1 이상 150,000 이하입니다.
    - s에는 '1'이 최소 하나 이상 포함되어 있습니다.
    
- [입출력 예]

    | s              | result |
    | -------------- | ------ |
    | "110010101001" | [3,8]  |
    | "01110"        | [3,3]  |
    | "1111111"      | [4,1]  |

- [문제 풀이]

  ```python
  ## Mine
  def solution(s):
      answer = [0, 0]
      while len(s) > 1:
          answer[0] += 1
          answer[1] += s.count('0')
  				s = s.replace('0', '')
          s = bin(len(s))[2:]
      return answer
  
    
  ## Others
  # 0이 아닌 1을 기준으로 잡아서 replace 없이 구현!
  def solution(s):
      cnt, zero = 0, 0
      while s != '1':
          cnt += 1
          one = s.count('1')
          zero += len(s) - one
          s = bin(num)[2:]
      return [cnt, zero]
  ```



### Day6

#### 숫자의 표현

- [문제 설명]

  Finn은 요즘 수학공부에 빠져 있습니다. 수학 공부를 하던 Finn은 자연수 n을 연속한 자연수들로 표현 하는 방법이 여러개라는 사실을 알게 되었습니다. 예를들어 15는 다음과 같이 4가지로 표현 할 수 있습니다.

  - 1 + 2 + 3 + 4 + 5 = 15
  - 4 + 5 + 6 = 15
  - 7 + 8 = 15
  - 15 = 15

  자연수 n이 매개변수로 주어질 때, 연속된 자연수들로 n을 표현하는 방법의 수를 return하는 solution를 완성해주세요.

- [제한 사항]

  • n은 10,000 이하의 자연수 입니다.

- [입출력 예]

  | n    | result |
  | ---- | ------ |
  | 15   | 4      |

- [문제 풀이]

  ```python
  ## Mine
  def solution(n):
      answer = 1
      for i in range(1, n+1):
          add = 0
          for j in range(i, n+1):
              if add < n:
                  add += j
              elif add == n:
                  answer += 1
                  break
              else:
                  add = 0  #초기화 안해줘도 작동하나, 초기화 했을 때 속도 미세하게 빠름
                  break
      return answer
  
    
  ## Others
  # 방법 1: while문 활용
  def solution(n):
      answer = 0
      for i in range(1, n+1):
          add = 0
          while add < n:
              add += i
              i += 1
          if add == n:
              answer += 1
      return answer
    
    
  # 방법 2-1: n의 약수 중 홀수의 개수와 같음!
  def solution(n):
      answer = 0
      for i in range(1,n+1) :
          if i % 2 != 0 and n % i == 0 :
              answer += 1
      return answer
    
    
  # 방법 2-2
  # Ex) i-1, i, i+1 -> 3i => 3의 배수, i-2, i-1, i, i+1, i+2 = 5i => 5의 배수
  def solution(n):
      return len([i  for i in range(1, n+1, 2) if n%i == 0])
  ```



### Day7

#### 피보나치 수

- [문제 설명]

  피보나치 수는 F(0) = 0, F(1) = 1일 때, 1 이상의 n에 대하여 F(n) = F(n-1) + F(n-2) 가 적용되는 수 입니다.

  예를들어

  - F(2) = F(0) + F(1) = 0 + 1 = 1
  - F(3) = F(1) + F(2) = 1 + 1 = 2
  - F(4) = F(2) + F(3) = 1 + 2 = 3
  - F(5) = F(3) + F(4) = 2 + 3 = 5

  와 같이 이어집니다.

  2 이상의 n이 입력되었을 때, n번째 피보나치 수를 1234567으로 나눈 나머지를 리턴하는 함수, solution을 완성해 주세요.

- [제한 사항]

  • n은 2 이상 100,000 이하인 자연수입니다.

- [입출력 예]

  | n    | return |
  | ---- | ------ |
  | 3    | 2      |
  | 5    | 5      |

- [문제 풀이]

  ```python
  ## Mine
  def solution(n):
      f = [0, 1]
      for i in range(1, n):
          f.append(sum(f[-2:]))
      return f[-1]%1234567
    
    
  ## Others
  def solution(n):
    	f1, f2 = 0, 1
      for i in range(1, n):
        	f1, f2 = f2, f1+f2
      return f2%1234567
  ```

  

