## network edge (1.2)

<br>

### A closer look at network structure :

- **network edge** : *host* 들을 이야기 한다. hosts는 clients와 servers를 이야기하고, server는 주로 data center에 있다.
- **access networks, physical media** : network edge 부분의 네트워크들을 가르키는 말이다. 유선일수도, 무선일수도 있다.
- **network core** : 위에서 이야기한 요소들을 연결해주는 router나 switch들이 있다.

<br>

### Access networks and physical media

**"edge router에 어떻게 end system이 연결될까?"**

집인 경우엔 **residential access network**를 연결하고, 학교나 조직에서는 **institutional access network**에 연결, 그리고 모바일은 **mobile access network**에 연결한다. 

<br>

`bandwidth` = 초당 몇 개의 비트를 보낼 수 있느냐? 

이 값은 접속망에 붙어있는 사용자가 몇명이냐에 따라 달라진다. 사람들이 많이 붙어서 데이터를 주고받으면 속도가 떨어진다. 

그러면 이 `bandwidth`를 내가 쓸 수 있는 양을 잘라서 주면 안되냐? 그래서 나온 개념이 shared와, dedicated이다. 

- **shared** : bandwidth를 공유해서 사용하는 것 → Internet이 채택하고 있는 개념
- **dedicated** : bandwidth를 할당받아서 사용하는 것 → 전화망이 채택하고 있는 개념

<br>

### Access network : digital subscriber line (DSL)

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/201530289-37b1b4a0-5f8a-45c5-8dd8-6df23a9ac215.png" width=800>
</p>
<br>

Access network의 한 예를 보여준다.

<br>

#### Access network란:question:

>**Access network**란 접속망을 뜻하며, end system이 네트워크에 연결되기 위해 제공되는 네트워크라고 할 수 있다. 쉽게 말해 네트워크에 접근하기 위한 네트워크이다. end system 들이 인터넷을 사용할 수 있도록 길을 열어주는 네트워크라고 보면 된다.
예를 들어, 스마트폰에서 wifi에 접속하거나 PC에 랜선을 꼽는 것 모두 엑세스 네트워크에 접속하는 것이라고 할 수 있다. U+나 KT같은 ISP가 access network를 제공해준다.

<br>

보통 통신사에서 연결 선을 주면, 전화, 인터넷, 텔레비젼으로 나눠진다. 음성과 데이터는 **shared**와 **dedicated**라는 다른 개념을 채택하고 있기 때문에, 다른 주파수에 실어서 통신하게 한다. 

보통 사람들이 업로드보다는 다운로드를 많이 하기 때문에 upstream과 downstream의 전송룰이 달라 asymmetric 하다고 한다.

**upstream** : 사용자 단에서 보내는 데이터

**downstream** : 사용자 단으로 내려오는 데이터

<br>

### Access network : cable network

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/201530628-286f2931-5cdc-4590-be80-d283cb984d69.png" width=700>
</p>
<br>

케이블이 집으로 들어오면, 텔레비젼과 인터넷, 전화까지 서비스를 하게 된다. 역시 이것도 주파수로 분리한다. 사이가 좁은 주파수가 높은 주파수이다. 높은 주파수와 낮은 주파수를 섞어서 보내게 되면, 수신단에서 이 두 주파수를 분리할 수 있다.

- 주파수 : 초당 시그널이 몇번 반복되느냐

**frequency division multiplexing** : 다른 주파수를 섞어서 보낸다. 그래서 주파수가 다르다라고 하면 다른 데이터를 보낼 수 있다는 것을 의미한다. 

그래서 9개의 각기 다른 주파수에 다른 데이터를 실어 보낼 수 있다. 

<br>

### Access network : cable network

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/201530713-12ef6e52-9e61-4460-8e73-0511742a9039.png" width=700>
</p>
<br>

**asymmetric** : upstream과 downstream 사이의 전송율이 다른 것을 의미한다. 

<br>

### Access network : home network

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/201530793-c8b100dc-a7b8-4d7e-99c6-e071aa116424.png" width=700>
</p>
<br>

밖에 있는 ISP로부터 집으로 인터넷이 들어온다고 할 때 **edge router**에 여러가지 장치들이 붙게 된다. cable이나 DSL 모뎀으로 연결이 된다.

- firewall : 보안에 관련된 일을 한다.
- NAT : 임의의 IP 주소를 할당받아서 집 안에서만 쓸 수 있게 한다.
- wired Ethernet (1Gbps) : 유선 이더넷 최대 1기가 bps 속도
- wireless access point (54 Mbps) : 와이파이 최대 54 메가 bps 속도

<br>

### Ethernet

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/201530845-35f75fa9-d9e4-4b4c-8dde-653ce79612f0.png" width=700>
</p>
<br>

과거의 유선 랜을 이야기 한다. 학교에 있는 수많은 컴퓨터들이 이더넷 스위치에 연결되어 있다. 요즘은 이더넷의 속도가 엄청 빨라졌다. 그래서 요즘은 국가 기관망에서도 많이 쓰인다. 

<br>

### wireless access networks

**wireless LANs** 

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/201530872-a88b0bfb-7489-40b2-b064-720356d59a5d.png" width=500>
</p>
<br>

- a.k.a wifi이다.
- 처음 속도 11에서 450까지 성장하였다.
- 비교적 근거리에서 사용가능하다.

**wide-area wireless access** 

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/201530920-e6c569e7-427c-4bef-ad72-90ed40e2c859.png" width=500>
</p>
<br>

- 기지국을 통해서 서비스하는 cellular 네트워크로, 과거에는 음성중심이었고, 지금은 스마트폰의 증가로 인터넷 영역으로 편입되었다.
- 비교적 장거리에서 사용가능하다.

<br>

### Host : sends packets of data

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/201530947-83c3098e-a525-43c4-90ed-63df4901916d.png" width=600>
</p>
<br>

호스트는 데이터를 전송하는 기능을 갖고 있다. 그래서 내가 보내려는 데이터를 **packet**으로 자른다. 

각각의 패킷의 길이를 **L**, 링크에서 보낼 수 있는 전송률을 **R** 이라고 하자. 

- 여기서 transmission rate R은 link transmission rate, link capacity, link bandwidth라고도 불리운다.

그러면 host에서 router로 데이터를 보내는데, packet의 **transmission delay**는 어떻게 될까? **L/R** 이다.

<br>

### Physical media

- bit : 0 또는 1의 한 개 단위
- physical link : transmitter와 receiver 간에 물리적으로 연결되어 있는 선
- guided media : 유선
- unguided media : 무선
- twisted pair (TP) : 카테고리에 따라서 전송속도가 다르다.

<br>

### Physical media : coax, fiber

- coaxial cable : 텔레비젼 뒤에 꼽혀있는 선
- fiber optic cable : 광케이블. 빛을 이용해서 신호를 쏴주기 때문에 전송율도 높고 에러도 적다. 장거리에 데이터를 보낼 때는 광케이블을 이용한다.

<br>

### Physical media : radio

무선은 선이 없기 때문에 신호가 퍼진다.