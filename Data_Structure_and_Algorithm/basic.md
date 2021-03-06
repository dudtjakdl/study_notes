> 해당 문서는 [Do it! 자료구조와 함께 배우는 알고리즘 입문 : 파이썬 편 (시바타 보요 저)](http://www.yes24.com/Product/Goods/91219874)을 보고 정리한 내용입니다.
- 본 문서에 작성된 코드는 **파이썬 (Python)** 으로 작성하였습니다.
- 책을 보며 공부하면서 도움이 된 파이썬 문법과 개념은 [Python 폴더](https://github.com/dudtjakdl/TIL/blob/main/Python)의 문서에 정리하였습니다.
- 그 외 추가 내용은 인터넷 검색을 통해 공부하고 덧붙여 정리하였습니다.
# 알고리즘

    알고리즘 (algorithm) : 어떠한 문제를 해결하기 위해 정해 놓은 일련의 절차


- 올바른 알고리즘이란 **어떠한 경우에도 실행 결과가 똑같이 나오는 것**을 말한다.
- 알고리즘(또는 프로그램)이 흐르는 방향은 **조건식**이 결정한다.  이때 조건식에 따라 알고리즘 흐름이 두 갈래로 나뉘는 것을 **양 갈래 선택**이라 한다.

- 같은 결과(해답)을 얻을 수 있는 알고리즘은 여러 개일 수 있다.

- 빠른 알고리즘은 많은 메모리를 요구한다.

## 구조적 프로그래밍
- 구조적 프로그래밍 (structured programming) : 입력과 출력으로 이루어진 구성 요소를 계층으로 배치하여 *순차, 선택, 반복* 세 종류의 제어 흐름을 통해 프로그램을 구성하는 방법

- 순차 구조 (sequential structure) : 한 문장씩 순서대로 처리되는 구조

- 선택 구조 (select structure) : 조건식으로 평가한 결과에 따라 프로그램의 실행 흐름이 변경되는 구조 

- 반복 구조 (repetition structure) : 어떤 조건이 성립하는 동안 반복해서 처리하는 구조. 일반적으로 루프 (loop) 라고 함 
    - 사전 판단 반복 구조 : 반복을 계속할 것인지를 판단하는 구조
    - 루프 본문 : 반복 대상이 되는 명령문
    - 카운터용 변수 : 반복을 제어할 때 사용하는 변수

- 분기 (branching) : 프로그램의 실행 흐름을 다른 곳으로 변경하는 명령

# 복잡도
알고리즘의 성능을 객관적으로 평가하는 기준을 **복잡도(complexity)** 라고 한다. 프로그램의 실행 속도는 프로그램이 동작하는 하드웨어나 컴파일러 등의 조건에 따라 달라진다.
    
- 시간 복잡도(time complexity): 실행하는 데 필요한 시간을 평가한다.
- 공간 복잡도(space complexity): 메모리(기억 공간)와 파일 공간이 얼마나 필요한지를 평가한다.

## 빅오(Big O) 표기법
알고리즘의 시공간 복잡도를 수학적으로 표시해주는 대표적인 방법이자, 알고리즘의 성능을 평가하는 척도이다.

![복잡도 그래프](https://media.vlpt.us/images/hyunju-song/post/46743924-afff-4a33-9d75-cd18bda96292/image.png)

    * 복잡도 증가율
    O(1) < O(log n) < O(n) < O(n log n) < O(n^2) < O(n^k) < O(2^n) < O(n!)
**빅오 표기법 규칙**

1. 가장 높은 차수만 남긴다.
    
    O(n² + n) -> O(n²)

2. 계수 및 상수는 버린다.

    O(2n + 3) -> O(n)

3. 즉, 전체 복잡도는 차원이 가장 높은 복잡도를 선택하는 것이다.
    
    O(f(n)) + O(g(n)) = O(max(f(n), g(n))) 

> 참고 https://velog.io/@raram2/big-o-notation-and-time-complexity

# 순서도 (Flowchart)
순서도는 문제를 정의, 분석하고 해결하는 방법을 그림으로 표현한 것이다.
## 순서도 기호

![순서도 기호](https://t1.daumcdn.net/cfile/blog/241B2C4358F7554338)
- 단말 : 프로그램 흐름의 시작과 종료를 나타냄
- 선 : 제어의 흐름을 의미
- 준비 : 기억장소, 초기값 등 작업의 준비 과정을 나타냄
- 처리 : 여러 종류의 처리 기능. 연산이나 연산 집합의 실행
- 입출력 : 기억 장치을 지정하지 않은 데이터 자체. 일반적인 입출력을 나타내기 위한 기호
- 판단(조건) : 기호 안에 정의한 조건을 평가하여 하나의 출구를 선택하는 판단 기능을 나타냄
- 종속처리 : 서브루틴이나 모듈 등 다른 곳에서 이미 정의한 하나 이상의 연산 또는 명령으로 이루어진 처리
- 연결자(결합) : 다음에 처리할 순서가 있는 곳으로 연결
# 자료구조

    자료구조 (data structure) : 데이터 단위와 데이터 자체 사이의 물리적 또는 논리적인 관계, 논리적인 관계로 이루어진 데이터 구성

자료구조를 알아야 하는 이유는 컴퓨터에서 처리해야 하는 많은 데이터를 모아 효율적으로 관리하고 구조화하는 데 있다.

# 배열

    배열 (array) : 번호와 번호에 대응하는 데이터들로 이루어져 묶음 단위로 값을 저장하는 자료 구조. 

- 배열에는 객체가 저장되며, 배열에 저장된 객체 하나하나를 **원소(element)** 라고 한다.
- 각 원소는 0, 1, 2, ... 순으로 **인덱스(index)** 를 부여받는다.
- 배열 원소를 하나씩 차례로 주목하여 살펴보는 방식을 알고리즘 용어로 **스캔(scan)** 이라 한다.

## 리스트 (list)

리스트는 원소를 변경할 수 있는 **뮤터블(mutable)** list 형 객체이다.

```python
list1 = []                 # [] 빈 리스트 생성
list2 = [1, 2, 3]          # [1, 2, 3]
list3 = ['A', 'B', 'C', ]  # ['A', 'B', 'C'] 맨 마지막 원소에 쉼표를 써도 됨

list4 = list()           # [] 빈 리스트 생성
list5 = list('ABC')      # ['A', 'B', 'C'] 각각의 문자로부터 원소 생성
list6 = list([1, 2, 3])  # [1, 2, 3] 리스트로부터 원소 생성
list7 = list((1, 2, 3))  # [1, 2, 3] 튜플로부터 원소 생성
list8 = list({1, 2, 3})  # [1, 2, 3] 집합으로부터 원소 생성

list9 = list(range(7))          # [0, 1, 2, 3, 4, 5, 6]
list10 = list(range(3, 8))      # [3, 4, 5, 6, 7]
list11 = list(range(3, 13, 2))  # [3, 5, 7, 9, 11]

lits12 = [None] * 5   # [None, None, None, None, None] 원소가 5개이면서 원소값이 없는 리스트
```

## 튜플 (tuple)

튜플은 원소에 순서를 매겨 결합한 것으로, 원소를 변경할 수 없는 **이뮤터블(immutable)** 자료형이다.

```python
tuple1 = ()              # ()
tuple2 = 1,              # (1,) 원소가 1개인 경우 쉼표 반드시 입력
tuple3 = (1,)            # (1,) 원소가 1개인 경우 쉼표 반드시 입력
tuple4 = 1, 2, 3         # (1, 2, 3)
tuple5 = 1, 2, 3,        # (1, 2, 3)
tuple6 = (1, 2, 3)       # (1, 2, 3)
tuple7 = (1, 2, 3, )     # (1, 2, 3)
tuple8 = 'A', 'B', 'C',  # ('A', 'B', 'C')

tuple9 = tuple()           # () 빈 튜플 생성
tuple10 = tuple('ABC')      # ('A', 'B', 'C') 문자열의 각 문자로부터 원소를 생성
tuple11 = tuple([1, 2, 3])  # (1, 2, 3) 리스트로부터 원소 생성
tuple12 = tuple({1, 2, 3})  # (1, 2, 3) 집합으로부터 원소 생성

tuple13 = tuple(range(7))         # (0, 1, 2, 3, 4, 5, 6)
tuple14 = tuple(range(3, 8))      # (3, 4, 5, 6, 7)
tuple15 = tuple(range(3, 13, 2))  # (3, 5, 7, 9, 11)
```
## 언팩 (unpack)

리스트나 튜플의 원솟값들을 풀어 여러 변수에 대입하는 것을 **언팩(unpack)** 이라 한다.
``` python
x = [1, 2, 3]   # 리스트 x 선언
a, b, c = x     # x를 언팩하여 변수 a, b, c에 대입
print(a, b, c)  # 1, 2, 3
```

## 슬라이스 (slice)

리스트 또는 튜플의 원소 일부를 연속해서 또는 일정한 간격으로 꺼내 새로운 리스트, 튜플을 만드는 것을 **슬라이스(slice)** 라고 한다.
```python
s[i:j]      # s[i]부터 s[j-1]까지 나열
s[i:j:k]    # s[i]부터 s[j-1]까지 k씩 건너뛰며 나열    
```

|패턴|설명|
|------|------|
|s[:]|리스트 s의 원소를 모두 출력|
|s[:n]|리스트 s의 원소 중 맨 앞에서부터 n개까지 출력|
|s[i:]|리스트 s의 원소 중 s[i]부터 맨 끝까지 출력|
|s[-n:]|리스트 s의 원소 중 -n에서부터 맨 끝까지 출력|
|s[::k]|리스트 s의 원소 중 맨 앞에서부터 k개씩 건너뛰며 출력|
|s[::-1]|리스트 s의 원소 중 맨 끝에서부터 전부 출력|



# 수학 개념

## 가우스의 덧셈
1부터 n까지 정수의 합은 ```n x (n + 1) / 2``` 로 구할 수 있다. 이를 가우스의 덧셈이라고 한다.
```python
sum = n * (n + 1) // 2
```

## 드모르간의 법칙
드로므간의 법칙은 '각 조건을 부정하고 논리곱을 논리합으로, 논리합을 논리곱으로 바꾸고 다시 전체를 부정하면 원래의 조건과 같다'는 법칙이다.

    1. x and y와 not(not x or not y)의 논릿값은 같다.
    2. x or y와 not(not x and not y)의 논릿값은 같다.