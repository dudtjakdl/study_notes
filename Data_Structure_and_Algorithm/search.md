> 해당 문서는 [Do it! 자료구조와 함께 배우는 알고리즘 입문 : 파이썬 편 (시바타 보요 저)](http://www.yes24.com/Product/Goods/91219874)을 보고 정리한 내용입니다.
- 본 문서에 작성된 코드는 **파이썬 (Python)** 으로 작성하였습니다.
- 책을 보며 공부하면서 도움이 된 파이썬 문법과 개념은 [Python 폴더](https://github.com/dudtjakdl/TIL/blob/main/Python)의 문서에 정리하였습니다.
- 그 외 추가 내용은 인터넷 검색을 통해 공부하고 덧붙여 정리하였습니다.

# 검색과 키
    검색 (search): 데이터 집합에서 원하는 값을 가진 원소를 찾아내는 행위
    키 (key): 검색 조건에서 주목하는 항목

대부분의 경우 키는 데이터의 일부이다. 데이터가 간단한 정수값이나 문자열이면 데이터값이 그대로 키값이 될 수도 있다. 검색에서 조건은 하나만 지정할 수도 있고, 논리곱 또는 논리합을 사용하여 복합 지정할 수도 있다.

# 검색 알고리즘 종류
- 배열 검색
    - 선형 검색 : 무작위로 늘어놓은 데이터 집합에서 검색을 수행
    - 이진 검색 : 일정한 규칙으로 늘어놓은 데이터 집합에서 아주 빠른 검색을 수행
    - 해시법 : 추가, 삭제가 자주 일어나는 데이터 집합에서 아주 빠른 검색을 수행

- 연결 리스트 검색

- 이진 검색 트리 검색

검색 시간, 계산 시간 뿐만 아니라 필요한 상황에 따라 용도, 목적, 실행 속도, 자료구조 등 여러 사항을 고려해서 *검색 이외의 작업에 들어가는 비용을 종합 평가하여 알고리즘을 선택*해야 한다.

# 배열 검색
## 선형 검색
    선형 검색 (linear search): 직선 모양(선형)으로 늘어선 배열에서 원하는 키값을 가진 원소를 찾을 때까지 맨 앞부터 스캔하여 순서대로 검색하는 알고리즘

- 배열 검색 중 가장 기본적인 알고리즘이다. 
- 무작위로 늘어놓은(정렬되지 않은) 데이터 집합에서 검색을 수행한다.
- 순차 검색(sequential search)라고도 한다.

**선형 검색의 종료 조건**
    
    1. 검색할 값을 찾지 못하고 배열의 맨 끝을 지나간 경우 -> 검색 실패
    2. 검색할 값과 같은 원소를 찾는 경우 -> 검색 성공

```python
def seq_search(a: Sequence, key: Any) -> int:
    """시퀀스 a에서 key값이 같은 원소를 선형 검색"""
    i = 0

    while True:
        if i == len(a):
            return -1  # 검색에 실패하여 -1을 반환
        if a[i] == key:
            return i   # 검색에 성공하여 현재 조사한 배열의 인덱스를 반환
        i += 1
```

### 보초법 (sentinel method)
선형 검색의 2가지 종료 조건 중, *검색할 값을 찾지 못하고 배열의 맨 끝을 지나간 경우를 판단하는 조건* ```if i == len(a)```을 없애기 위한 방법.

*검색하고자 하는 키값을 배열의 맨 끝에 삽입*하여, 반복을 종료하는 판단 횟수를 줄일 수 있다. 이때 배열 끝에 삽입하는 데이터를 **보초(sentinel)** 이라 한다.

```python
def seq_search(seq: Sequence, key: Any) -> int:
    """시퀀스 seq에서 key와 일치하는 원소를 선형 검색(보초법)"""
    a = copy.deepcopy(seq)  # seq를 복사
    a.append(key)           # 보초 key를 추가
 
    i = 0
    while True:
        if a[i] == key: 
            break  # 검색에 성공하면 while 문을 종료
        i += 1
    return -1 if i == len(seq) else i  # 찾은 원소가 배열의 원래 데이터인지 보초인지 판단 
```

반복문이 종료되면 찾은 원소가 배열의 원래 데이터인지 보초인지 판단한다. i 값이 len(seq)와 같으면 검색에 실패한 것을 나타내는 -1을 반환하고, 그렇지 않으면 검색 성공이므로 인덱스 i를 반환한다.

## 이진 검색
    이진 검색 (binary search): 원소가 오름차순이나 내림차순으로 정렬된 배열에서 좀 더 효율적으로 검색할 수 있는 알고리즘

- 배열의 데이터가 정렬되어 있어야 한다.
- 선형 검색보다 빠르게 검색할 수 있다.

## 해시법
추가, 삭제가 자주 일어나는 데이터 집합에서 아주 빠른 검색을 수행한다.

### 체인법
같은 해시값 데이터를 연결 리스트로 연결하는 방법이다.
### 오픈 주소법
데이터를 위한 해시값이 충돌할 때 재해시하는 방법이다.