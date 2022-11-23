## The network core (1.3)

<br>

### The network core

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/203464864-de14dc17-f9a4-49ae-adcd-f1a06bf125be.png" width=400>
</p>
<br>

**네트워크 코어**는 위의 그림과 같이, 전체 네트워크 시스템의 중앙에 위치하여 **데이터를 전송하는 핵심적인 역할**을 한다. 

- **mesh of interconnected routers** : 수많은 라우터들이 그물처럼 얽혀있는 구조를 띈다.
- **packet-switching** : 네트워크 코어에서 패킷을 교환하는 것을 말한다.
    - 유선이나 무선으로 연결된 유저들이 어플리케이션 층에서 만든 메세지를 패킷으로 쪼갠다.
    - 이 패킷들이 라우터들을 건너건너 전송된다.

패킷이 왔다갔다 하는 과정이 어떻게 되는지를 이 과목을 통해서 배우게 된다. 

<br>

### **Packet-switching : store-and-forward**

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/203465085-e3b3e0a5-1e26-40a0-aeb5-57b1e95fe922.png" width=800>
</p>
<br>

패킷은 **store-and-forward** 방식으로 전송되는데, 이는 라우터가 하나의 패킷을 다 받고, 그 다음에 전송하는 방법이다.

각 번호대로 패킷이 하나씩 가는데 (보내는 쪽 `source` → 받는 쪽 `destination`), 이때 보내려는 패킷의 단위가 **L bits**이고, 이를 **R bps**로 보낸다. 

<br>

**L/R** → L bits를 R bps로 보낼 때 걸리는 시간 

- ex) 7.5 bit를 1.5 bps로 보낼 때 걸리는 시간은? one-hop transmission delay는 5초이다.

<br>

**bandwidth가 크면 클수록 빠르게 보낼 수 있다.** 

<br>

### **Packet-switching : queueing delay, loss**

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/203465345-8f7a57fc-21cc-4461-a5cd-bac0dfee3ea9.png" width=800>
</p>
<br>

보내는 소스가 두 개, 그리고 목적지도 복수 개 일 때, A에서는 녹색인 패킷이, B에선 파란색인 패킷이 날라온다. 이때 모종의 순서로 날라오게 되는데, 이때 여러 소스가 **bandwidth**를 공유해서 날라온다. 

여기서 문제는 bandwidth를 절반씩 딱 잘라서 공유하지 않을 수 있다. A는 별로 데이터를 안보내고, B가 많이 보낸다 하면 B가 bandwidth를 더 많이 쓸 수 있다는 것이다. 

여기서 **인터넷의 철학**이 나온다. bandwidth를 칼같이 나누지 않고, 많으면 많은대로 적으면 적은대로 내보내도록 한다. 

<br>

그렇다면 이때 생길 수 있는 문제는 A와 B가 많은 데이터를 내보내려고 한다면, **bandwidth가 꽉 차는 문제**가 생길 수 있다.

→ 라우터들은 전부 **queue**를 가지고 있고, 들어온 순서대로 처리를 하게 된다. 문제는 처리하는 속도보다 들어오는 양이 너무 많을 수 있다는 것이다. 큐가 무한히 길어질 수 있다는 것.. 큐의 용량을 넘어서까지 들어오면 **drop(lost)** 을 시켜버린다. 삭제하게 되면 어떻게 될까? 나는 보냈는데 데이터가 없어져부러.. 아무리 기다려도 응답이 오지 않는 상태가 발생한다. 

인터넷 트래픽이 특정 시간에 몰리는 이유도 **bandwidth를 공유하는 인터넷의 철학** 때문이다. 

bandwidth가 충분한데 라우터 큐의 용량이 부족한 경우, 혹은 반대인 경우도 마찬가지이다.

<br>

**queueing delay** : 라우터의 큐에서 대기하고 있는 delay이다. 앞선 transmission delay와는 다른 delay이다. memory (buffer) 를 queue라고 한다. 

인터넷의 컨셉은 너가 보내는 것을 무조건 보장해줄게가 아니라 "일단 최선을 다해서 보내는데 보장은 못해. 알아서 써라.. 난 모르겠다이"

→ 어? 근데 이럼 너무 불합리한거 아냐? 그래서 drop 되지 않고 품질이 보장되는 네트워크를 설계해보자 하는 시도가 당연히 있었다. 

<br>

### **Two key network-core functions**

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/203465728-ec07d05b-7ff8-466b-b87c-e0f3b5b04eb3.png" width=800>
</p>
<br>

- **routing** : 어떤 라우터를 거쳐서 갈거냐?를 결정하는 것이 라우팅 이슈. 즉 forwarding table을 만드는 과정이다. routing algorithms으로 결정한다.
- **forwarding** : 위의 알고리즘에 따라서 경로가 결정되면 내보야 하는데 이 내보내는 것을 forwarding 이슈. 즉, forwarding table을 읽어서 라우터의 Input으로 들어오는 패킷을 올바른 output으로 보내는 기능이다.

<br>

### **Alternative core : circuit switching**

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/203465859-ef8b44ef-3791-42ee-b707-b8fe90500129.png" width=500>
</p>
<br>

위에서 말한 품질이 보장되는 네트워크 설계에 대한 이야기를 해보자.

**circuit switching**은 패킷을 보낼 때 예약을 하는 것이라고 할 수 있다. 그래서 보장이 되게 하는 것!

만약 10명을 받을 수 있는데 11명이 들어온다면 마지막 1명은 블락해서 막는 방법을 사용해서 앞서 들어온 사람들이 메세지를 안전하게 보낼 수 있도록 보장한다. 

앞서 말한 인터넷은 오는 대로 다 받는다. 이에 반해 **circuit switching**은 리소스를 할당하고 다른 소스와 공유하지 않는다.

<br>

### Circuit switching : FDM versus TDM

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/203466167-ad4ae1bc-ebb9-44da-b586-bed4148a5c06.png" width=800>
</p>
<br>

**FDM** : bandwidth를 쪼개서 나눠주는 것을 **FDM**이라고 한다. 고속도로를 n개의 차선으로 나누어 사용하는 것과 같은 개념

**TDM** : 시간 단위로 쪼개서 나눠주는 것을 **TDM**이라고 한다. 몇 개의 채널들이 한 링크의 시간을 분할하여 사용한다.

즉, FDM에서는 대역의 일부를 공유한다면 TDM은 시간을 공유한다. 

bandwidth 자원을 이야기 할 땐, 주파수와 시간을 이야기 한다. 

<br>

### **Packet switching versus circuit switching**

bandwidth가 1Mb/s이고 각 유저가 활동중일 때는 100kb/s를 전송하고 전체 시간의 10%가 활동중이라고 할때, 

**circuit-switching** : 10명의 유저의 전송을 보장할 수 있다. 

**packet switching** : 35명 중에 10명의 사용자가 활동중일 확률은 10프로다. 0.0004라는 확률이기 때문에 그냥 둬도 상관없을 것 (확률적으로만 따진다면)

이것만 보더라도 packet switching 방법이 더 적합한 방법같다 보인다. 

<br>


그럼 **packet switching**이 **winner일까**?

- **bursty data**(지속적으로 오는 데이터가 아닌, 간헐적으로 오는 데이터)인 경우에는 압도적으로 좋다
    - 리소스 공유
    - 심플하게 쓰게 하는 것이 좋겠다. call setup 필요없이 들어오는 대로 쓰게하는 것이 좋겠다.
- **congestion** (혼잡한 상태)에는 packet의 delay나 loss가 생길 수 있다. 그럼 어떻게 하면 신뢰성을 높일 수 있을까? 하는 것이 고민거리
    - 그래서 나온 프로토콜이 **TCP**이다.
- 어떻게 circuit switching의 장점을 뽑아쓸 수 있을까?
    - bandwidth가 필요한 경우에는 보장하는 것도 좋겠다. 이후 강의에서 다루게 된다.

<br>

### **Internet structure : network of networks**

- **end systems**들은 **access ISPs**를 통해 인터넷에 연결된다.
    - 우리 학교의 경우 아주대의 ISP에 연결되어 있다.
- **Access ISP**들은 상호 연결되어 있어야한다.
    - 두 hosts가 서로 패킷을 보낼 수 있도록 해야한다.

<br>


<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/203466500-ba116aef-3bca-4be1-99cc-339d2792851b.png" width=800>
</p>
<br>

어떻게 ISP들이 연결될 수 있게 할거냐? 모든 access network끼리 상호 연결하는 방법이 있다.

그런데 이렇게 해서는 개수를 감당할 수 없다. **doesn’t scale !!**

<br>

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/203466611-d1762b42-d239-49ca-acc7-4e9cbc83acd2.png" width=800>
</p>
<br>

이런식으로 중간에 거대한 ISP(Global ISP)를 두고 연결하면 괜찮을 거 같다. 

<br>

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/203466673-305d2b4c-333d-4722-ba87-e5f4904c6fba.png" width=800>
</p>
<br>

또는 큰 ISP 복수 개를 두어 연결을 담당할 수 있다. ISP는 자체 망을 이루고 있다. 
이 ISP들을 어떻게 연결할까? 땅 속에 케이블을 깔아서 연결시킬 수 있다. 

해저케이블을 통해서 국가 간에 연결도 가능하다. 이런식으로 전 세계를 묶을 수 있다는 것. 

중간중간 regional net이 있을 수도 있다. 그래서 인터넷을 **네트워크들의 네트워크**라고 표현하는 것이다. 

<br>


<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/203466846-f1a6eb56-8bdb-41a7-a873-98f3d5d4f49b.png" width=800>
</p>
<br>

또한 구글이나 마이크로소프트 등과 같은 **Content provider network**들이 자체 네트워크를 돌릴 수도 있다.

유튜브같은 경우 bandwidth가 많이 사용된다. 그래서 전세계의 ISP의 bandwidth를 잡아먹게 되는데, 이걸 어찌할까 고민하다가 구글이 자체적인 Content provider network를 고안해서 물리게 된다. 전세계 라우터의 50퍼를 구글이 깔았다고 한다.

<br>

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/203466941-a3353ee4-6fd6-41d7-ac27-c08d1d93af0a.png" width=800>
</p>
<br>

**Tier 1** → 우리나라로 치면 국가 기관 망 국가 전체를 연결해주는 ISP

그 아래 Regional ISP가 있고, 또 그 아래 access ISP가 있다.

근데 이 그림을 보면 Google이 Tier 1 위치에 있다. 자체적인 서비스를 위해서 저정도의 규모를 가지게끔 하였다.

<br>

### Tier 1 ISP : e.g., Sprint

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/203467183-1a1ee528-895e-433f-9c07-e64882d4371a.png" width=800>
</p>
<br>

미국의 Tier 1 예시, 마름모로 표시된 지역을 거점으로 하여 연결했다.