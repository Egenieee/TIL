## What is the Internet (1.1)

- 여기서  관사 “_the_”가 붙고 대문자 “_I_”로 시작하는 것이 중요.
- **인터넷**은 수 많은 네트워크중 하나의 네트워크를 말한다.
- 네트워크는 뭘까? 한국말로 하면 “망”이다. **여러 개체들이 연결된 것**을 의미한다.

<br>

### What is the Internet : “nuts and bolts” view

<br>
<p align="center"><img width=500 alt="" src="https://user-images.githubusercontent.com/81270604/200702217-8e132529-d01d-4482-8481-91bec0209e2e.png"></p>
<br>

ISP끼리 연결되면? 전 세계가 연결된다. → Internet이 되는 것.

***“인터넷이 무엇인가?”*** 에 대한 질문에 인터넷의 구성요소를 기술함으로써 설명한다. 즉, 인터넷을 구성하는 기본적인 하드웨어와 소프트웨어 요소를 기술함으로써 설명한다는 것이다.

- **billions of connected computing devices** : 네트워크를 실질적으로 이용하는 사용자단을 <u>end systems</u> 또는 <u>hosts</u>라고 한다. 이 기기 들은 communication links와 packet switches로 이루어진 네트워크에 연결되어 있으며 network app(웹 브라우저, 모바일 앱 등 네트워크를 통해서 무언가를 주고 받는 모든 것들을 통칭한다)을 실행한다.
- **communication links** : 중간에 있는 것들끼리 연결시키거나, 중간에 있는 것들과 end system을 연결시켜주는 것을 말한다. 즉 유무선으로 이루어진 연결 장치들을 이야기 한다. fiber, copper은 **유선**, radio, satellite는 **무선**이다. 여기서 transmission rate는 전송률을 뜻한다. 1초에 얼마나 많은 비트(not BYTE)를 보낼 수 있는 지 나타내는 척도다. bandwidth라고도 불린다. 앞으로 수업에서는 bandwidth라는 단어로 통일한다.
- **packet switches** : 데이터를 흐를 수 있게 하는 장치를 이야기 한다. 데이터(이 과목에서는 packet이라고 칭한다.)의 경로를 결정한다. router나 switches가 있다. 데이터가 흐르는 방향을 잡아주는(?) 용도

<br>

**참고**
**packet**은 network layer에서의 **데이터 단위**이다. 

- 한 end system이 다른 end system에 보낼 데이터를 가지고 있을 때, 송신 end system은 그 데이터를 segment로 나누고 각 segment에 header를 붙인다. 이렇게 만들어진 정보 패키지는 컴퓨터 네트워크에서 **packet**(패킷)이라고 불린다. 패킷은 destination end system으로 네트워크를 통해 보내지고, destination에서 원래의 데이터로 다시 조립된다.

<br>

집에서 사용하는 home network는 **regional ISP**(Internet Service Providers)에 물리게 되는 것이다. ISP끼리 연결이 되어 있기 때문에 우리가 해외 웹에도 접속을 할 수 있는 것이다. 모바일 네트워크또한 ISP에 연결되어 있다. 결국 크게 보면 다 얽히고 섥혀있다. 

- **router** : Data 경로를 찾아서 이동시켜준다. 알고리즘에 의해서 경로를 찾는다. 라우터는 보통 네트워크 코어에서 사용된다.

- **switch** : 보통 access network에서 사용된다.

- **path** : 패킷이 송신 end system에서 수신 end system에 도달하는 동안 거쳐 온 일련의 link와 switch들을 네트워크 상의 path 또는 route라고 한다.  

- **node** : router, end system 등 요소 하나 하나를 이야기 한다. 수업 추후엔 Nodes라고 칭한다. 

<br>

### “Fun” Internet-connected devices

인터넷이 연결된 재미난 디바이스들~

<br>

<p align="center"><img src="https://user-images.githubusercontent.com/81270604/200702278-dee57098-e945-456e-a57e-6bd0575fddf4.png" width=800></p>

<br>

**IoT** : Internet of Things

<br>

### What is the Internet : “nuts and bolts” view

- **Internet** : “network of networks” 네트워크들 중의 네트워크란 뜻이져? **ISP**들이 서로 연결된 것을 의미한다. 여기서 **ISP**는 Internet Service Providers의 약자로 **regional ISP**는 KT, U plus, SKT 등등을 의미한다.
- **protocols** : 컴퓨터나 원거리 통신 장비 사이에서 메시지를 주고 받는 양식과 규칙의 체계이다. [[위키백과]](https://ko.wikipedia.org/wiki/%ED%86%B5%EC%8B%A0_%ED%94%84%EB%A1%9C%ED%86%A0%EC%BD%9C) 예를 들어 TCP, IP, HTTP, Skype, 802.11 등이 있다. 프로토콜은 인터넷에서 Data를 주고 받을 때 필수인 개념이다.
- **Internet standard** : 인터넷 표준이란 뜻이져?
    - Data들을 보내는 순서 등을 약속을 맺고 보내자!
    - RFC : RFC 문서는 비평을 기다리는 문서라는 의미로, 컴퓨터 네트워크 공학 등에서 인터넷 기술에 적용 가능한 새로운 연구, 혁신, 기법 등을 아우르는 메모를 나타낸다. [[위키백과]](https://ko.wikipedia.org/wiki/RFC)
    - IETF : Internet Engineering Task Force의 약자로 국제 인터넷 표준화 기구이다. 인터넷의 운영, 관리, 개발에 대해 협의하고 프로토콜과 구조적인 사안들을 분석하는 인터넷 표준화 작업기구이다. [[위키백과]](https://ko.wikipedia.org/wiki/%EA%B5%AD%EC%A0%9C_%EC%9D%B8%ED%84%B0%EB%84%B7_%ED%91%9C%EC%A4%80%ED%99%94_%EA%B8%B0%EA%B5%AC)

<br>

### What is the Internet : a service view

두번째로 인터넷에 대해서 설명하는 방법은 분산 애플리케이션에 서비스를 제공하는 **네트워킹 인프라 구조 관점**에서 인터넷을 기술하는 것이다.

- **infrastructure that provides services to applications** : 인터넷은 어플리케이션에 서비스를 제공하는 기반시스템이다.
- **provides programming interface to apps** : 인터넷은 여러가지 앱들에 대한 프로그래밍 인터페이스를 제공한다.

<br>

### What’s a protocol?

프로토콜이란, 일종의 약속이다. 사회에는 수많은 프로토콜들이 있다. 

**network protocols** : 컴퓨터들이 서로 상호간에 **데이터를 잘 주고받을 수 있도록 만든 약속**이다. 즉, 컴퓨터들이 다 똑같이 이해할 수 있도록 데이터를 전달하는 약속, 규범이다. 

프로토콜은 주고받는 메세지의 `format`, `order` 을 정의한다. 

<br>


![image](https://user-images.githubusercontent.com/81270604/200702344-2555ade8-71b7-4088-9828-604d5e4b73ee.png)

`client` 와 `server` 간의 대화를 나타낸다. 

`client`가 `server`에게 원하는 데이터를 요청하고 `server`는 원하는 데이터를 보내준다. 

→ 이런 것들이 전부 **프로토콜**이다.