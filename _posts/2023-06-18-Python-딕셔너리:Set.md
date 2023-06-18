# 딕셔너리 Dictionary
Hash, Map이라고도 한다. 

- 키 + 값(Key + Value)으로 구성된 한 쌍의 데이터를 답을 수 있는 자료구조
- 키는 종복 불가
- 값은 중복 가능
- `{}`중괄호로 표현한다. 

## 딕셔너리의 기본 사용법

```python 
doc = {}
doc = {1: "a", False: [1, 4, 56], (1, 2): "tuple"}
print(doc[False]) # -> [1, 4, 56]
print(doc.get(False)) # -> [1, 4, 56]

# 원소 추가
doc[3.14] = True
print(doc[3.14]) # -> True

# 원소 업데이트
doc[1] = "b"
print(doc[1])  # -> "b"

# 원소 길이 반환
len(doc) # -> 4

# in 사용 가능
if False in doc:
	print(doc[False])

# del삭제 함수
del(doc[False])
# 
```
## 딕셔너리 특별 사용법

### 딕셔너리.get(키)
해당 키의 값을 가져올 수 있고, 없는 키이면 `None`을 반환함.

### 딕셔너리.update(`{키1: 값1, 키2: 값2}`)
한 번에 여러 개의 `키:값`을 수정하는 방법

### 딕셔너리.clear()
딕셔너리 전체 삭제

## 딕셔너리 For문

### `for i in dic`: 
for문에서 i는 키를 사용함. 

```python
d = { 1 : 2, False : 20, (1, 2) : "튜플" } 
for i in dic:
    print(f"{key}:{dic[key]}")
```

### `for i in dic.keys()`: 
for문에서 i는 키를 사용함. 

```python
d = { 1 : 2, False : 20, (1, 2) : "튜플" } 
for i in dic.keys():
    print(f"{key}:{dic[key]}")
```

### `for i in dic.values()`: 
값들을 사용함. 

```python
d = { 1 : 2, False : 20, (1, 2) : "튜플" } 
for i in dic.values():
    print(i)
```

### `for k, v in dic.items()`: 
키, 값을 동시에

```python
d = { 1 : 2, False : 20, (1, 2) : "튜플" } 
for k, v in dic.items():
    print(k, v)
```


# 집합 Set
수학에서의 집합을 나타나는 것

## 집합 특징

- **순서 없음**
- **중복 없음**
- 교집합, 합집합, 차집합 연산 가능
- 중괄효`{}`로 표시
- 특정 원소로 접근 불가
- 집합안에 리스트는 포함 안됨.  (리스트 대신 튜플 저장 가능)

## 집합 생성
`{1, "a", (1,3)}`처럼 하드 코등 가능
`set()`함수 안에 문자열, 리스트, 튜플 등 객체를 전달하면 집합으로 반환해줌

```python
set([1, "b"]) # -> {1, 'b'}
set("yellow") # -> {'y', 'o', 'w', 'l', 'e'}
set((1, "word")) # -> {'word', 1}
```
## 집합 원소 추가

### set.add()
단일 원소 추가 시 사용

```python
a = set([1, "buy"])
a.add("C") # -> {'C', 1, 'buy'}
```

### set.update()
여러 원소 추가 시 사용

```python
a = set([1, "buy"])
a.update("car") # -> {1, 'c', 'buy', 'a', 'r'}
a.update([9, 78]) # -> {1, 'c', 'buy', 'a', 9, 78, 'r'}
```

## set.remove(원소) -> 집합 원소 삭제

```python
a = set([1, "buy"])
a.remove("1") # -> {'buy'}
```

## 집합 연산(교, 합, 차집합)

### `&` 또는 `set1.intersection(set2)`
교집합

```python
s1 = { 1, 2, 20, (1, 2), "문자열" } 
s2 = { 1, 2, 3 }
ints = s1 & s2 # -> {1, 2}
ints = s1.intersection(s2) # -> {1, 2}
```

### `|` 또는 `set1.union(set2)`
합집합

```python
s1 = { 1, 2, 20, (1, 2), "문자열" } 
s2 = { 1, 2, 3 }
ints = s1 | s2 # -> {1, 2, '문자열', (1, 2), 20, 3}
ints = s1.union(s2) # -> {1, 2, '문자열', (1, 2), 20, 3}
```

### `-` 또는 `set1.difference(set2)`
합집합

```python
s1 = { 1, 2, 20, (1, 2), "문자열" } 
s2 = { 1, 2, 3 }
ints = s1 - s2 # -> {(1, 2), '문자열', 20}
ints = s1.difference(s2) # -> {(1, 2), '문자열', 20}
```

## `in`: 집합 안 원소 존재 여부

```python 
if "a" in set1:
print(True)
```


