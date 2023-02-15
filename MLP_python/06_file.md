# file 로 부터 읽고 쓰기
- file 작업 시 일반적인 업무순서
	
	1. file 핸들러 개체를 생성
		```python
			f = open('test.txt','r')
			f2 = open( 'test2.txt','w')
		```
	2. file 핸들러를 이용하여 읽거나 쓰기 작업을 진행
		```python
			mydata = f.read()
			f2.write( mydata )
		```
	3. file 핸들러 닫기
		```python
			f.close()
			f2.close()
		```

- file 처리모드

|`open()` 메서드 <br>file 처리모드|의미 |
|:-:|:-:|
|r| 읽기 전용|
|w|쓰기전용 (존재하는 내용 삭제)|
|a|파일의 끝에 추가|
|r+|읽고 쓰기모드|
|w+|읽고 쓰기모드(기존 내용 삭제)|
|a+|읽고 쓰되 추가모드|
|...기타 생략|....|

-	`.read()`
	- 파일 읽기
- `.write(내용)`
	- 내용을 쓰기 , 내용에 리스트도 가능 
- `.writelines(리스트)`
	- 리스트로 저장시
- `.readline()`
	- 한줄 읽기
- `.readlines()`
	- 한꺼번에 읽기


## pickle 모듈
- 구조화된 객체를 파일에 저장 및 복원해주는 모듈
- 문자열로의 변환 등의 절차가 필요없다.
	- `pickling` (object serialization)
		- 객체가 저장되기 위해  바이트 스트링으로 변환되는 과정
	- `unpickling` (object deserialization)
		- 바이트 스트링에서 원본객체로 복원되는 과정

- 저장작업
	```python
		import pickle
		# 피클모듈 임포트
		f = open(파일명,w)
		# 파일 오픈
		pickle.dump(데이터,f)
		# 데이터 저장
		f.close()
		# 파일클로즈
	```

- 읽기작업
	```python
		import pickle
		# 피클모듈 임포트
		f = open(파일명,r)
		# 파일 오픈
		data = pickle.load(f)
		# 데이터 읽기
		f.close()
		# 파일클로즈
	```
