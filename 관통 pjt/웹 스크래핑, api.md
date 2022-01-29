### 웹 스크래핑

#웹사이트의 정보를 가져오고 싶다(requests)

`import requests`

```python
#정보가 있는 url로 요청을 보낸다

url =_________________________
response = requests.get(url).text

```



#원하는 정보 가져오기 (BeautifulSoup)

```
from bs4 import BeautifulSoup
```

```python
#html 파일에 있는 데이터를 가져오기
data = beautiftlSoup(response, 'html.parser')

# 선택자를 통해 내가 원하는 정보를 가져오기(f12 - 선택 - copy selector)
kospi = data.select_one('#KOSPI_now') #selector
print(kospi.text)
```





### API

(application programming interface)

컴퓨터나 컴퓨터 프로그램 사이의 연결

일종의 소프트웨어 인터페이스이며 다른 종류의 소프트웨어에 서비스를 제공

사용하는 방법을 기술하는 문서나 표준은 api 사양/명세

```
import requests

url = 

#요청 이미 json파일로 제공이 됨
reponse = requests.get(url).json()
print(response)
```

```
url = 기본
params = {
      'name' : '원하는 이름'
}

response = requests.get(url, params = params).json()
```



요청하는 방식 이해 

인증방식

url생성

  기본주소,  원하는 기능에 대한 추가 경로, 요청 변수

응답결과에 대한 이해

응답 결과 타입(json)

응답 결과 구조

``` 
import requests

# url 및 요청변수 설정
base_url = 기본url
path = '/movie/now_playing'
params = { 
     `api_key': '8838732987'
     'region': 'KR'
     'langeage': 'ko'
}

#요청 보낸 결과 저장
response = requests.get(Base_url+ath,params=params)
print(response.status_code, response.url)
data = response.json()

#조작
print(response)

```

너무 많이 출력돼서 보기 불편할 때 보기 편하게 하는 법

json viewer에 print(response.status_code, response.url) 결과 보기