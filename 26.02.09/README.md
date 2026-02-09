# 제어문

## if 문 **


```python
if True:
    print("조건문 실행")
```

    조건문 실행



```python
# if 구문

money = "돈있어"

if money == "돈있어":
    print("택시타고가")
else:
    print("걸어가")
```

    택시타고가


<table style="float:left">
<thead>
<tr>
<th>비교연산자</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr>
<td>x &lt; y</td>
<td>x가 y보다 작다.</td>
</tr>
<tr>
<td>x &gt; y</td>
<td>x가 y보다 크다.</td>
</tr>
<tr>
<td>x == y</td>
<td>x와 y가 같다.</td>
</tr>
<tr>
<td>x != y</td>
<td>x와 y가 같지 않다.</td>
</tr>
<tr>
<td>x &gt;= y</td>
<td>x가 y보다 크거나 같다.</td>
</tr>
<tr>
<td>x &lt;= y</td>
<td>x가 y보다 작거나 같다.</td>
</tr>
</tbody>
</table>


```python
if money != "돈없어":
    print("과자 사먹자")
```

    과자 사먹자


### in, not in
<table style="float:left">
<thead>
<tr>
<th>in</th>
<th>not in</th>
</tr>
</thead>
<tbody>
<tr>
<td>x in 리스트</td>
<td>x not in 리스트</td>
</tr>
<tr>
<td>x in 튜플</td>
<td>x not in 튜플</td>
</tr>
<tr>
<td>x in 문자열</td>
<td>x not in 문자열</td>
</tr>
</tbody>
</table>


```python
print(1 in [1, 2, 3])
print(1 not in [1, 2, 3])
print('j' not in "python")
```

    True
    False
    True



```python
pocket = ['paper', 'key', 'money']
if money in pocket:
    print("택시를 타고가라")
else:
    print("걸어가라")
```

    걸어가라



```python
pocket = ['paper', 'key', 'money']
if 'money' in pocket:
    pass
else:
    print("걸어가라")
```


```python
# 조건부 표현식1
age = 19
status = "성인" if age >= 18 else "미성년"
print(status)

# 조건부 표현식2
temperature = 25
weather = "따뜻함" if temperature > 20 else "추움"
print(weather)

# 조건부 표현식3
money = 1500
transportation = "버스" if money >= 1000 else "도보"
print(transportation)
```

    성인
    따뜻함
    버스



```python
# if elif
pocket = ['paper', 'key']
card = True
if 'money' in pocket:
    print("돈으로 택시 타라")
elif card == True:
    print("카드로 택시 타라")
else:
    print("걸어가라")
```

    카드로 택시 타라



```python
# if만 사용
pocket = ['paper', 'key']
card = True
if 'money' in pocket:
    print("돈으로 택시 타라")
if card != True:
    print("카드로 택시 타라")
if not 'money' in pocket and not card == True:
    print("걸어가라")
```

### 문제 및 실습


```python
# 문제
# 만약 5000원 이상의 돈을 가지고 있으면 택시를 타고가고, 그렇지 않으면 걸어가라

money = input("얼마가 있나요?")

if int(money) >= 5000:
    print("택시를 타고가라")
else:
    print("걸어가라")
```

    얼마가 있나요? 5000


    택시를 타고가라



```python
# 문제2
identify = True # "있다"
stamp = True # "있다"
sign = True # "할수있다"

print("어서오세요.")
inp1 = "있다" in input("신분증이 있나요?")
inp2 = "있다" in input("도장이 있나요?")
inp3 = "있다" in input("싸인할 수 있나요?")
inp4 = "한국" in input("국적이 어딘가요?")

if (inp1 and (inp2 or inp3)) and not inp4:
    print("업무 진행 가능합니다.")
else:
    print("서류가 부족합니다.")
```

    어서오세요.


    신분증이 있나요? 있음
    도장이 있나요? 있음
    싸인할 수 있나요? 없음
    국적이 어딘가요? 미국


    서류가 부족합니다.



```python
# 문제3
dic = {"name": "hong", "age": 23, "gender": "male"}

# 나이가 20살 이상이며 성별이 male이면 군대가기
if dic["age"] >= 20 and dic["gender"] == "male":
    print("군대가기")
else:
    pass
```

    군대가기



```python
# 조건부 표현식
# 조건부 표현식에서는 pass문을 쓸 수 없음
print("군대가기" if dic["age"] >= 20 and dic["gender"] == "male" else "")
```

    군대가기



```python
# 응용1 (if elif)
score = 80
```

### while 문 **


```python
check = 0
while check < 10:
    check += 1
    print("가자", check)
    
check = 0
while check < 10:
    print("가자", check)
    check += 1
```

    가자 1
    가자 2
    가자 3
    가자 4
    가자 5
    가자 6
    가자 7
    가자 8
    가자 9
    가자 10
    가자 0
    가자 1
    가자 2
    가자 3
    가자 4
    가자 5
    가자 6
    가자 7
    가자 8
    가자 9



```python
coffee = 5
money = 300
while money:
    print("돈을 받았으니 커피를 줍니다.")
    coffee = coffee -1
    print("남은 커피의 양은 %d개입니다." % coffee)
    if coffee == 0:
        print("커피가 다 떨어졌습니다. 판매를 중지합니다.")
        break
```

    돈을 받았으니 커피를 줍니다.
    남은 커피의 양은 4개입니다.
    돈을 받았으니 커피를 줍니다.
    남은 커피의 양은 3개입니다.
    돈을 받았으니 커피를 줍니다.
    남은 커피의 양은 2개입니다.
    돈을 받았으니 커피를 줍니다.
    남은 커피의 양은 1개입니다.
    돈을 받았으니 커피를 줍니다.
    남은 커피의 양은 0개입니다.
    커피가 다 떨어졌습니다. 판매를 중지합니다.



```python
# 응용
import random as ran

li = []
i = 0
cc = int(input("몇 회 주사위를 던질까요?") or 100)
while i < cc:
    num = ran.randint(1, 6)
    li.append(num)
    i += 1

if cc == len(li):
    print(f"{cc} 회 정상 진행 되었습니다.")
    print("1번이 %d번 등장 %.2f%%" % (li.count(1), ((li.count(1)/i)*100)))
    print("2번이 %d번 등장 %.2f%%" % (li.count(2), ((li.count(2)/i)*100)))
    print("3번이 %d번 등장 %.2f%%" % (li.count(3), ((li.count(3)/i)*100)))
    print("4번이 %d번 등장 %.2f%%" % (li.count(4), ((li.count(4)/i)*100)))
    print("5번이 %d번 등장 %.2f%%" % (li.count(5), ((li.count(5)/i)*100)))
    print("6번이 %d번 등장 %.2f%%" % (li.count(6), ((li.count(6)/i)*100)))
else:
    print(f"검증 결과 이상이 있습니다. {cc}회 목표로 동작하였으나, {len(li)}으로 측정되었습니다.")
```

    몇 회 주사위를 던질까요? 1000


    1000 회 정상 진행 되었습니다.
    1번이 162번 등장 16.20%
    2번이 174번 등장 17.40%
    3번이 156번 등장 15.60%
    4번이 183번 등장 18.30%
    5번이 171번 등장 17.10%
    6번이 154번 등장 15.40%



```python
# 로또 번호
# 1 ~ 45 임의의 수 중에서 중복없는 6개의 수를 뽑아 나열하여 분석하시오.
import random as ran

li = []

while len(li) < 6:
    num = ran.randint(1, 45)
    if num not in li:
        li.append(num)
        
li.sort()
print(li)
```

    [9, 13, 18, 24, 33, 37]



```python

```
