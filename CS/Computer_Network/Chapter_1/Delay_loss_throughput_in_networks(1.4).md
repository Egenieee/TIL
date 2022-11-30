## Delay, loss throughput in networks (1.4)

<br>

### How do loss and delay occur?

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/204769835-6fbd8069-a5ff-4982-9675-174a3179a6d1.png" width=800>
</p>
<br>

이는 앞에서 말했던 딜레이다. 각각의 라우터에는 버퍼가 있는데, 패킷 도착률이 output link의 capacity를 일시적으로 초과하게 되면 생기게 된다.

<br>

### Four sources of packet delay

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/204770196-aeb8744c-1967-4726-95c0-e341389c06c1.png" width=800>
</p>
<br>

딜레이에는 네 가지 유형이있다.  

- **transmission delay** : bandwidth로 보내는 시간. 즉 라우터가 패킷을 link로 밀어내는 시간을 의미한다.
- **queneing delay** : 라우터의 버퍼, 즉 큐에서 기다리는 시간
- **propagation delay** : 라우터에서 라우터로 가는 물리적 시간. 가까우면 가까울 수록 이 시간이 짧다.
- **processing delay** : 비트 단위로 패킷을 받아 에러를 점검하고, 아웃풋 링크를 정하는데 걸리는 시간

이 네가지 딜레이를 더한 것이 **total delay** 값이다. 

수강신청이 잘 되려면 ? propagation delay가 짧고, bandwidth가 커야 한다 즉 인터넷 속도가 빨라야 한다. 

<br>

>**이해를 돕기위한 추가 설명!** 
>전송이 끝나는 즉시 전파가 시작된다. 패킷의 Head는 가장 먼저 전송이 끝나 전파되기 시작하였고, 가장 먼저 전파되었기 때문에 Receiver에게 가장 먼저 도착할 것이다. 패킷의 끝인 Tail까지 전송이 끝나게 되면 패킷의 전송을 끝이 나게 되고 패킷 전체가 전파 중인 상태가 된다.

<br>


transmission delay : L/R

propagation delay : 거리 나누기 속도 d/s (km → m로 환산해서 문제 풀자)

queueing delay는 학부 과정에서 계산하지 않는다.
processing delay는 통상 얼마인지 가정한다. 

<br>

### Caravan analogy

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/204770762-12605b42-7c9a-4b39-b0f2-bec2e225d8f5.png" width=800>
</p>
<br>

10대의 자동차가 톨게이트에 진입한다. 나가는 톨게이트는 **100km** 떨어져 있다. 들어와서 나갈 때 까지 얼마나의 딜레이가 있을까? 자동차는 시속 **100km/h**로 가정한다.

한 차당 서비스하는 시간이 **12초**가 걸린다고 하자. 이게 링크로 밀어넣는 **transmisson delay**이다.

자동차를 bit로 보자. 10 bit → 1 packet

10대가 지나가려면 120초가 걸린다. → **transmission delay**(bandwidth가 크면 클수록 이 시간이 빨라진다.)

각각의 차가 톨게이트 → 톨게이트 가는 시간 1시간 → **propagation delay**

총 delay는 1시간 + 120초 = 62분 **transmission delay + propagation delay**

<br>

### Caravan analogy (more)

자동차들이 시속 **1000km/h**로 달린다면? 그리고 한 차당 1분 동안의 서비스 시간이 걸린다고 가정하자.

100km를 달리는데 걸리는 시간은 6분이다.

**propagation delay** : 6분

**transmission delay** : 1분

**7분**이 지나면 첫번째 자동차가 두번째 돌게이트에 도착한다.

<br>

### Queueing delay (revisited)

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/204770791-40bbfd72-537b-49af-9610-4cedd813c888.png" width=500>
</p>
<br>

어떨 때는 **transmisson**이 클 때가 있고, 어떤 때는 **propagation**이 더 클 때도 있다. 

위의 자동차 예에서 첫번째 예는 propagation이 크고 두번째는 반대의 상황이다.

end 유저 입장에서 딜레이가 왜 생기는 지 알 수가 없고 추정을 할 수 있는데,

- propagation delay가 문제 될 때 : 위성에 문제가 있을 때

- transmission delay가 문제될 때 : 데이터 보내는 경우에 속도가 느릴 때

예를 들어, 인터넷 속도 빠른데 잘 안된다? 또는 친구는 되는데 나는 안된다? 이는 **queueing delay**일 수 있다.

여기서 **a**(average packet arrival rate)를 곱한 값을 **traffic intensity**라고 하는데 이 값이 1이 되면 포화상태이다. queueing delay가 무한대로 올라간다. 꽉 찼다는 이야기져.. 1만 돼도 딜레이가 무한에 가까워진다. 이런 일이 일어나지 않게 해야한다. 일부러 드랍을 더 시키기 위해서 큐의 메모리를 제한한다.

<br>

### Packet loss

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/204770812-7698f78f-ca46-4846-b55f-d050bfd0bbd3.png" width=800>
</p>
<br>

**큐** 또는 **버퍼**가 꽉차서 **드랍**을 하는 바람에 패킷 손실이 얼마나 났는지 나타내는 표현이다.

요청에서 손실이 났는지, 응답에서 손실이 났는지 모르겠지만 loss가 생겼다는 것이다. 
그러면, 이 손실을 어떻게 detect할건데? 이 신뢰성에 대한 문제는 **TCP**에서 다룬다. 

<br>

### Troughput

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/204770851-48eb883b-d690-47b5-94d7-6562ba3ed405.png" width=800>
</p>
<br>

`sender`에서 데이터를 보내서 `receiver`가 받게 되는데, **link capacity**가 서로 다르기 때문에 **좁은 쪽**에 맞춰지게 된다. 즉 `sender`/`receiver` 사이에서 통과되는 데이터의 양이 얼마인지를 **throughput**이라고 한다. 여러 사용자들이 **bandwidth를 공유**하기 때문에 내가 얼마나 쓸 수 있는지는 모른다. 

instantaneous는 잘 알 수가 없어서 average로 얼마나 쓰고 있는지 측정한다.

어느 날엔 유튜브가 느리다? Throuput이 떨어지는 날. 반대면 좋은 날

한 마디로 througput은 **성능**이다. 단위 시간 동안 `sender`와 `receiver`가 교환한 **데이터의 양**을 이야기 한다. throughput은 link의 bandwidth가 고정되었다 하더라도, 망상태에 따라서 달라지기도 한다. 

<br>

### Troughput (more)

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/204770887-f612530a-f060-41f8-ade9-edcbe5b4914f.png" width=800>
</p>
<br>

위 그림에서는 $R_s$에 의해서 Troughput이 결정된다.

<br>

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/204770913-19bf70c0-9418-4719-b742-c6b9f517c4e6.png" width=800>
</p>
<br>

위 그림에서는 $R_c$에 의해서 Troughput이 결정된다.

**bottlenenk link**는 네트워크 각 link의 capacity가 다를 수 있는 상황에서 데이터를 전송할 때 가장 좁은 길을 파악해서 그 좁은 길의 용량만큼을 보내게 되는데, 가장 좁은 길을 **bottleneck**이라고 한다. 

결국 이 **bottleneck link**가 전체 성능을 좌지우지 하게된다. 

<br>

### Troughput: Internet scenario

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/81270604/204770957-fb2aa17e-e1a4-4bf3-98a6-8877195dac55.png" width=400>
</p>
<br>

`client`에서 `server`로 데이터가 왔다갔다 하는데, 어디가 **bottleneck**이 될까?

`server`는 보통 bottleneck이 잘 안된다. 그치만 트래픽이 몰릴 때 bottleneck이 생길 수밖에 없다. 중간 부분을 백본 네트워크라고 하는데, 이런 쪽도 사실 보틀넥은 안된다. 국가기관망인데 보틀넥이 되면 큰일난다. 

결국 아랫부분 `client`들이 붙어있는 **access network**가 bottleneck이 된다. 보통 무선으로 연결하는 경우가 많기 때문에 더더욱 bottleneck이 된다 (무선이 유선보다 bancwidth가 낮기 때문)

셋 중 가장 작은 것이 **bottleneck**이 된다.