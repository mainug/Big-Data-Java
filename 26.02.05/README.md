## 튜플 자료형


```python
t1 = ()
t2 = (1,) # *
t3 = (1, 2, 3)
t4 = 1, 2, 3 # *
t5 = ('a', 'b', ('ab', 'cd'))
```


```python
# 주의점
t2 = (4234,)
print(type(t2))
t4 = 123
print(type(t4))
```

    <class 'tuple'>
    <class 'int'>



```python
# 튜플 요소값 삭제
t1 = (1, 2, 'a', 'b')
# del t1[1]
```

**튜플은 요소 삭제 안됨**

![image.png](475d38f3-2b79-418c-b231-db5ffb7cce37.png)


```python
t1 = (1, 2, 'a', 'b')
# t1[0] = 'c'
```

**튜플은 요소 변경 안됨**

![image.png](22568e98-5f15-46c2-8dcf-fe0c243617f0.png)


```python
# 인덱싱 하기
t1 = (1, 2, 'a', 'b')
print(t1[0])
print(t1[3])
```

    1
    b



```python
# 슬라이싱
t1 = 1, 2, 'a', 'b'
print(t1[1:])
```

    (2, 'a', 'b')



```python
# 튜플 더하기
t1 = (1, 2, 'a', 'b')
t2 = (3, 4)
t3 = t1 + t2
t3
```




    (1, 2, 'a', 'b', 3, 4)




```python
# 튜플 곱하기
t2 = (3, 4)
t3 = t2 * 3
t3
```




    (3, 4, 3, 4, 3, 4)




```python
# 튜플 길이 구하기
t1 = (1, 2, 'a', 'b')
len(t1)
```




    4



## 딕셔너리 자료형 


```python
# 딕셔너리 초기화
dic0 = {}
print(dic0, type(dic0))
dic1 = dict()
print(dic1, type(dic1))
```

    {} <class 'dict'>
    {} <class 'dict'>



```python
# 딕셔너리 만들기
dic = {'name': 'pey', 'phone': '010-9999-1234', 'birth': '1118'}
dic1 = {0: 'pey', 1: '010-9999-1234', 2: '1118'}
```

<table style="float:left">
<thead>
<tr>
<th>key</th>
<th>value</th>
</tr>
</thead>
<tbody>
<tr>
<td>name</td>
<td>pey</td>
</tr>
<tr>
<td>phone</td>
<td>010-9999-1234</td>
</tr>
<tr>
<td>birth</td>
<td>1118</td>
</tr>
</tbody>
</table>


```python
# 쌍 추가
print(dic)
dic['address'] = "서울"
print(dic)
```

    {'name': 'pey', 'phone': '010-9999-1234', 'birth': '1118'}
    {'name': 'pey', 'phone': '010-9999-1234', 'birth': '1118', 'address': '서울'}



```python
# 숫자 키
dic1[1] = "일"
print(dic1)
```

    {0: 'pey', 1: '일', 2: '1118'}



```python
# 문자로 된 숫자 키
dic1["1"] = "일"
print(dic1)
```

    {0: 'pey', 1: '일', 2: '1118', '1': '일'}



```python
# 딕셔너리 내부 다른 자료형
dic['리스트'] = [11, 22, 33]
dic['튜플'] = 44, 55, 66
dic['딕셔너리'] = {"name": "홍길동"}
print(dic)
```

    {'name': 'pey', 'phone': '010-9999-1234', 'birth': '1118', 'address': '서울', '리스트': [11, 22, 33], '튜플': (44, 55, 66), '딕셔너리': {'name': '홍길동'}}



```python
# 쌍 삭제
del dic1['1']
print(dic1)
```

    {0: 'pey', 1: '일', 2: '1118'}



```python
# 문제
name = {"김연아": "피겨스케이팅", "류현진": "야구", "손흥민": "축구", "귀도": "파이썬"}
# 변경 - 김연아 : 은퇴
name["김연아"] = "은퇴"
print(name)
# 추가 - 김연경 : 배구
name["김연경"] = "배구"
print(name)
# 삭제 - 귀도
del name["귀도"]
print(name)
```

    {'김연아': '은퇴', '류현진': '야구', '손흥민': '축구', '귀도': '파이썬'}
    {'김연아': '은퇴', '류현진': '야구', '손흥민': '축구', '귀도': '파이썬', '김연경': '배구'}
    {'김연아': '은퇴', '류현진': '야구', '손흥민': '축구', '김연경': '배구'}



```python
# 주의사항
# key가 두개 이상이면 안된다
a = {1: 'a', 1: 'b'}
print(a)
# key값에는 리스트나 딕셔너리같은 mutable 형식이 되면 안된다. (튜플 가능)
# a = {[1, 2]: "hi"}
# key 값에 딕셔너리?
# a = {{1: "hello"}: "hi"}
```

    {1: 'b'}


**리스트를 key로 사용한 경우**

![image.png](a1d1e5d5-449f-4a58-b89a-fcd818b62b00.png)

**딕셔너리에 딕셔너리를 key로 사용한 경우**

![image.png](cbdf97e8-4603-4248-9f82-8ec460edf25c.png)

### 딕셔너리 관련 함수


```python
# keys - 키 리스트 만들기
a = {'name': 'pey', 'phone': '010-9999-1234', 'birth': '1118'}
ky = a.keys()
l_ky = list(ky)
print(ky) # key값만 담은 리스트 객체 반환
print(ky, type(a), type(ky), type(l_ky), sep="\n")
print(a)
```

    dict_keys(['name', 'phone', 'birth'])
    dict_keys(['name', 'phone', 'birth'])
    <class 'dict'>
    <class 'dict_keys'>
    <class 'list'>
    {'name': 'pey', 'phone': '010-9999-1234', 'birth': '1118'}



```python
# values - 값 리스트 만들기
a = {'name': 'pey', 'phone': '010-9999-1234', 'birth': '1118'}
va = a.values()
l_va = list(va)
print(va) # key값만 담은 리스트 객체 반환
print(va, type(a), type(va), type(l_va), sep="\n")
print(a)
```

    dict_values(['pey', '010-9999-1234', '1118'])
    dict_values(['pey', '010-9999-1234', '1118'])
    <class 'dict'>
    <class 'dict_values'>
    <class 'list'>
    {'name': 'pey', 'phone': '010-9999-1234', 'birth': '1118'}



```python
# items - 키, 값 쌍을 리스트안의 튜플로 만들기
a = {'name': 'pey', 'phone': '010-9999-1234', 'birth': '1118'}
it = a.items()
l_it = list(it)
print(it) # key값만 담은 리스트 객체 반환
print(it, type(a), type(it), type(l_it), sep="\n")
print(a)
```

    dict_items([('name', 'pey'), ('phone', '010-9999-1234'), ('birth', '1118')])
    dict_items([('name', 'pey'), ('phone', '010-9999-1234'), ('birth', '1118')])
    <class 'dict'>
    <class 'dict_items'>
    <class 'list'>
    {'name': 'pey', 'phone': '010-9999-1234', 'birth': '1118'}



```python
# clear - 키, 값 쌍 모두 지우기
a = {'name': 'pey', 'phone': '010-9999-1234', 'birth': '1118'}
print(a)
a.clear()
print(a)
```

    {'name': 'pey', 'phone': '010-9999-1234', 'birth': '1118'}
    {}



```python
# get - 키로 값 얻기
a = {'name': 'pey', 'phone': '010-9999-1234', 'birth': '1118'}
# 없는 키면 오류 발생
print(a['name'])
# 없는 키면 "None" 반환
print(a.get('address'))
# 없는 키일 때 "None"이 아닌 다른 문자열 반환
print(a.get('address', "없습니다"))
```

    pey
    None
    없습니다


**해당 값이 없을 때 오류**

![image.png](1142ad4f-1c57-4405-9019-672f7083596f.png)


```python
# in - 해당 키 값 조사하기 **
a = {'name': 'pey', 'phone': '010-9999-1234', 'birth': '1118'}
print("name" in a)
print("ok" in a)
```

    True
    False



```python
# pop - 가져와서 삭제하기
a = {'name': 'pey', 'phone': '010-9999-1234', 'birth': '1118'}
pp = a.pop("name")
print("꺼낸 값:", pp)
print("남은 값:", a)
```

    꺼낸 값: pey
    남은 값: {'phone': '010-9999-1234', 'birth': '1118'}



```python
# 응용 실습
import requests as r
url = "https://www.koreaexim.go.kr/site/program/financial/exchangeJSON?authkey=3spOQb36RyxH4cbtYdC1igtjlbe6K1YU&data=AP01"
result = r.get(url).json()
# print(result, type(result)) # json 형식으로 받으면 타입이 리스트임
print(result[-1]['cur_unit'], ":", result[-1]['deal_bas_r'])
```

    USD : 1,451.2



```python
# 이전에 알아낸 실시간 비트코인 BTC / USD 가격으로
# 실시간 환율을 계산하여 지금 비트코인 가격을 원화로 표시하시오.
# py 파일로 저장하여 python3로 실행하시오.
import requests as r
btc = "https://api4.binance.com/api/v3/ticker/price?symbol=BTCUSDT"
usd = "https://www.koreaexim.go.kr/site/program/financial/exchangeJSON?authkey=3spOQb36RyxH4cbtYdC1igtjlbe6K1YU&data=AP01"
r1 = r.get(btc).json()
r2 = r.get(usd).json()
r3 = float(r1['price']) * float(r2[-1]['deal_bas_r'].replace(',', ''))
print(f"{int(r3):,}", "원")
```

    103,543,178 원


**JSON**

배열 자료형, 키-값 쌍 등으로 이루어진 데이터 오브젝트를 전달하기 위해 인간이 읽을 수 있는 텍스트를 사용하는 개방형 표준 포맷.
요는 데이터를 전달해야 할 때 필요한 양식의 개념이다.

## 집합 자료형


```python
# 집합 자료형 초기화
s = set()
print(s, type(s))
```

    set() <class 'set'>



```python
# set 자료형 중복 허용 안함
li = [1, 2, 3]*2 + [1, 22, 33]*3
print(li)
s1 = set(li)
print(s1)
```

    [1, 2, 3, 1, 2, 3, 1, 22, 33, 1, 22, 33, 1, 22, 33]
    {1, 2, 3, 33, 22}



```python
# set 자료형 순서 없음, 인덱싱으로 요소값 얻을 수 없음
s2 = set("Hello")
print(s2)
```

    {'l', 'o', 'H', 'e'}



```python
s1 = set([1, 2, 3])
# print(s1[1])
l1 = list(s1)
print(l1)
print(l1[0])
t1 = tuple(s1)
print(t1)
print(t1[0])
```

    [1, 2, 3]
    1
    (1, 2, 3)
    1


**인덱싱으로 요소값 얻기 불가**

![image.png](0f0038f6-9acb-4b6e-bbb1-10afd6c748a1.png)


```python
# 문제
access_logs = ["192.168.0.1", "192.168.0.2", "192.168.0.1",
              "10.0.0.1", "192.168.0.2", "192.168.0.5"]
a = set(access_logs)
a.add("192.168.0.99")
print(a)
```

    {'192.168.0.99', '10.0.0.1', '192.168.0.1', '192.168.0.5', '192.168.0.2'}



```python
# 교집합, 합집합, 차집합
s1 = set([1, 2, 3, 4, 5, 6])
s2 = set([4, 5, 6, 7, 8, 9])
print("교집합", s1 & s2) # s1.intersection(s2) 가능
print("합집합", s1 | s2) # s1.union(s2) 가능
print("차집합", s1 - s2) # s1.difference(s2) 가능
```

    교집합 {4, 5, 6}
    합집합 {1, 2, 3, 4, 5, 6, 7, 8, 9}
    차집합 {1, 2, 3}


### 집합 자료형 관련 함수


```python
# add - 집합 자료형 값 1개 추가
s1 = set([1, 2, 3])
print(s1)
s1.add(4)
print(s1)
```

    {1, 2, 3}
    {1, 2, 3, 4}



```python
# update - 집합 자료형 값 여러 개 추가
s1 = set([1, 2, 3])
print(s1)
s1.update([2, 3, 4, 5, 6, 7])
print(s1) # 중복을 허용하지 않기에 2, 3 은 2개가 되지 않음
```

    {1, 2, 3}
    {1, 2, 3, 4, 5, 6, 7}


**값이 1개만 들어 갈 경우 오류**

![image.png](9e35f3d1-9c05-44c6-b6a5-0d59b6bcc5b5.png)


```python
# remove - 집합 자료형 특정 값 제거하기
s1 = set([1, 2, 3])
print(s1)
s1.remove(2) # index가 아닌 값으로 선택
print(s1)
```

    {1, 2, 3}
    {1, 3}


**존재하지 않는 값을 넣으면 오류**

![image.png](5280751f-c1ed-40e4-8003-fa3e53fddcee.png)


```python
# discard - 집합 자료형 특정 값 제거하기
s1 = set([1, 2, 3])
print(s1)
s1.discard(4) # 없는 값을 제거하려 해도 오류 발생X
print(s1)
```

    {1, 2, 3}
    {1, 2, 3}



```python
# clear - 집합 자료형 내 모든 값 제거
s1 = set([1, 2, 3])
s1.clear()
print(s1)
```

    set()


## 불 자료형


```python
a = True
b = False
print(type(a), type(b))
```

    <class 'bool'> <class 'bool'>



```python
a = 13 > 4
print(a, type(a))
a = 13 < 4
print(a, type(a))
a = 13 == 4
print(a, type(a))
a = 13 != 4
print(a, type(a))
```

    True <class 'bool'>
    False <class 'bool'>
    False <class 'bool'>
    True <class 'bool'>


<table style="float:left">
<thead>
<tr>
<th>값</th>
<th>참 or 거짓</th>
</tr>
</thead>
<tbody>
<tr>
<td>"python"</td>
<td>참</td>
</tr>
<tr>
<td>""</td>
<td>거짓</td>
</tr>
<tr>
<td>[1, 2, 3]</td>
<td>참</td>
</tr>
<tr>
<td>[]</td>
<td>거짓</td>
</tr>
<tr>
<td>(1, 2, 3)</td>
<td>참</td>
</tr>
<tr>
<td>()</td>
<td>거짓</td>
</tr>
<tr>
<td>{'a': 1}</td>
<td>참</td>
</tr>
<tr>
<td>{}</td>
<td>거짓</td>
</tr>
<tr>
<td>1</td>
<td>참</td>
</tr>
<tr>
<td>0</td>
<td>거짓</td>
</tr>
<tr>
<td>None</td>
<td>거짓</td>
</tr>
</tbody>
</table>


```python
print("python", bool("python"), sep=" : ")
print("\"\"", bool(""), sep=" : ")
print("[1, 2, 3]", bool([1, 2, 3]), sep=" : ")
print("[]", bool([]), sep=" : ")
print("(1, 2, 3)", bool((1, 2, 3)), sep=" : ")
print("()", bool(()), sep=" : ")
print("{'a': 1}", bool({'a': 1}), sep=" : ")
print("{}", bool({}), sep=" : ")
print("1", bool(1), sep=" : ")
print("0", bool(0), sep=" : ")
print("None", bool(None), sep=" : ")
```

    python : True
    "" : False
    [1, 2, 3] : True
    [] : False
    (1, 2, 3) : True
    () : False
    {'a': 1} : True
    {} : False
    1 : True
    0 : False
    None : False


### 논리 연산자


```python
# and 연산자
print(True and True)
print(True and False)
print(False and True)
print(False and False)
```

    True
    False
    False
    False



```python
# or 연산자
print(True or True)
print(True or False)
print(False or True)
print(False or False)
```

    True
    True
    True
    False



```python
# not 연산자
print(not True)
print(not False)
print(not 1)
print(not 0)
```

    False
    True
    False
    True



```python

```
