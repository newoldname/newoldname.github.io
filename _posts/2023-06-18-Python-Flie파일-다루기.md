## 파일 시스템을 파이썬으로 다루기
### 현재 경로
```python
import os
os.getcwd()
```

## 파일 열고 닫기
```python
# 파일_변수 = open(파일_이름)
f = open("../temp/abc.txt")

# 파일_변수.close()
f.close()
```

## 파일 읽기
- 파일을 읽는 방식이 다양하다
	- 한 번에 다 읽기
	- 한줄씩 읽기
	- 반복자를 이용해 한줄씩 처리학
	- 한 줄씩 읽고 리스트로 반환하기

### f.read()

```python
f = open("t.txt")
s = f.read() # 내용 전체 읽기
```

### f.readline()

```python
line = f.readline() # 한 줄씩 읽기
while line:
	print(line, end = " ")
	line = f.readline() 
```

### 파일 객체의 반복자 활용

```python
for oneLine in f:
	print(oneLine, end="") # oneLine 안에 이미 \n이 들어가 있어서 끝에 없이 처리
```

### f.readlines()

```python
lines = f.readlines() # 전체 읽고, 한줄씩 읽고 리스트로 반환
f.close()
```
## 파일 쓰기

### open("file_name", "w")
파일을 새로 만들어서 쓰기

```python
f = open("t.txt", "w")
f.write("hello Python") # 반환값: 12 -> 파일에 추가한 글자수를 int형으로 반환
```

### open("file_name", "a")
기존의 파일에 추가해서 쓰기

```python
f = open("t.txt", "a")
f.write("hello Python") # 반환값: 12 -> 파일에 추가한 글자수를 int형으로 반환
```

## with ... as ...:
관련이 있는 연산을 같이 수행할 때 사용함

```python
with open("t.txt", "r") as f:
	for line in f:
		print("line", end=")
	# 이 때 close를 따로 하지 않아도 됨. 
```

## 인코딩/디코딩
`open()`함수를 사용할 때 `encoding="utf-8"`처럼 지정할 수 있다. 

```python
with open("python.txt", "w", encoding="utf-8") as f:
	f,write("Hellooooooooo")
```

### local.getpreferredencoding()
컴퓨터의 인코딩 방식을 알 수 있다. 

```python
import locale
locale.getpreferredencoding() # -> 'cp949' / 'utf-8' 
```

###  UnicodeDecodeError 
파일 인코딩 방식과 `local.getpreferredencoding()`가 다를 때 방생

###  UnicodeEncodeError 
특정 인코딩 방식으로 저장할 수 없는 문자가 있을 때 발생


