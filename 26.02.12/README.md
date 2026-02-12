# 입출력제어

## 파일 생성 및 추가하기


```python
!pwd
```

    /home/pmw/data



```python
f = open("새파일이에요.txt", "w")
f.close()
```

<table style="float:left">
<thead>
<tr>
<th>파일열기모드</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr>
<td>r</td>
<td>읽기 모드: 파일을 읽기만 할 때 사용한다.</td>
</tr>
<tr>
<td>w</td>
<td>쓰기 모드: 파일에 내용을 쓸 때 사용한다.</td>
</tr>
<tr>
<td>a</td>
<td>추가 모드: 파일의 마지막에 새로운 내용을 추가할 때 사용한다.</td>
</tr>
</tbody>
</table>


```python
# 리눅스에서
f = open("/home/pmw/test.txt", "w")
f.close()
```


```python
f = open("새파일이에요.txt", "w")

for i in range(0, 20, 2):
    f.write(str(i) + "\n")

f.close()
```


```python
import requests as req

f = open("즐겨찾기종목.txt", "a")
url = "https://finance.naver.com/sise/sise_market_sum.naver"
ori = req.get(url).text

code = ['005930', '000270', '005380', '012450']

def finance(code = '005930'):
    start_title = ori.find(f'<a href="/item/main.naver?code={code}" class="tltle">삼성전자</a>')
    ori1 = ori[start_title : start_title + 70].replace(f'<a href="/item/main.naver?code={code}" class="tltle">', '').replace('</a></td>', '').replace('\n', '').strip()
    ori2 = ori[start_title + 70 : start_title + 105].replace('<td class="number">', '').replace('</td>', '').strip()
    print("종목:", ori1)
    print("가격:", ori2, "원")
    result = "종목:" + ori1 + "\n" + "가격:" + ori2 + "\n"
    f.write(result)

for x in code:
    finance(x)

f.close()
```

    종목: 삼성전자
    가격: 178,400 원
    종목: 
    가격: <title>시가총액 : Np 원
    종목: 
    가격: <title>시가총액 : Np 원
    종목: 
    가격: <title>시가총액 : Np 원


## 파일 읽어 오기


```python
import requests as req

url = "https://api4.binance.com/api/v3/ticker/price?symbol=BTCUSDT"
res = req.get(url).text
r = res.find("price")
bc = res[29:34]
print("비트코인 가격(달러): $" + bc)
won = str(int(res[29:34]) * 1450) 
print("비트코인 가격(원):", ((won[-12:-8] + "억") if won[-12:-8] else ""), won[-8:-4], '만', won[-4:], '원')
```

    비트코인 가격(달러): $67260
    비트코인 가격(원):  9752 만 7000 원



```python
import random as ran

f = open("로또추천.txt", "w")

for i in range(10):
    li = []
    while len(li) < 6:
        num = ran.randint(1, 45)
        if num not in li:
            li.append(num)
    li.sort()
    print(li)
    f.write(str(li) + "\n")
    
f.close()
```

    [1, 15, 23, 35, 42, 44]
    [11, 13, 17, 28, 31, 34]
    [7, 8, 11, 15, 23, 31]
    [3, 8, 16, 20, 27, 35]
    [8, 12, 19, 21, 34, 40]
    [10, 19, 24, 32, 33, 37]
    [20, 22, 35, 36, 39, 44]
    [8, 10, 11, 25, 28, 45]
    [6, 24, 37, 42, 43, 44]
    [6, 10, 22, 23, 26, 28]



```python
import time as t

f = open("./로또추천.txt", "r")

while 1:
    line = f.readline().strip()
    if not line: break
    print(line, end="\r")
    t.sleep(1)
    print(" "*15, end="\r")
f.close()
```

                    26, 28]]


```python
f = open("./로또추천.txt", "r")
print(f.readlines())
f.close()
```

    ['[1, 15, 23, 35, 42, 44]\n', '[11, 13, 17, 28, 31, 34]\n', '[7, 8, 11, 15, 23, 31]\n', '[3, 8, 16, 20, 27, 35]\n', '[8, 12, 19, 21, 34, 40]\n', '[10, 19, 24, 32, 33, 37]\n', '[20, 22, 35, 36, 39, 44]\n', '[8, 10, 11, 25, 28, 45]\n', '[6, 24, 37, 42, 43, 44]\n', '[6, 10, 22, 23, 26, 28]\n']



```python
f = open("./로또추천.txt", "r")
print(f.read())
f.close()
```

    [1, 15, 23, 35, 42, 44]
    [11, 13, 17, 28, 31, 34]
    [7, 8, 11, 15, 23, 31]
    [3, 8, 16, 20, 27, 35]
    [8, 12, 19, 21, 34, 40]
    [10, 19, 24, 32, 33, 37]
    [20, 22, 35, 36, 39, 44]
    [8, 10, 11, 25, 28, 45]
    [6, 24, 37, 42, 43, 44]
    [6, 10, 22, 23, 26, 28]
    



```python
f = open("./로또추천.txt", "r")
for line in f:
    print(line, end="")
f.close()
```

    [1, 15, 23, 35, 42, 44]
    [11, 13, 17, 28, 31, 34]
    [7, 8, 11, 15, 23, 31]
    [3, 8, 16, 20, 27, 35]
    [8, 12, 19, 21, 34, 40]
    [10, 19, 24, 32, 33, 37]
    [20, 22, 35, 36, 39, 44]
    [8, 10, 11, 25, 28, 45]
    [6, 24, 37, 42, 43, 44]
    [6, 10, 22, 23, 26, 28]



```python
f = open("./로또추천.txt", "r", encoding='UTF-8')
print(f)
f.close()
```

    <_io.TextIOWrapper name='./로또추천.txt' mode='r' encoding='UTF-8'>



```python
f = open("./로또추천.txt", "a")
f.write(f"내 로또 번호\n[1, 2, 3, 4, 5, 6]")
f.close()
```


```python

```
