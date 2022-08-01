# Double Linked List

### 🤷🏻‍♀️ Double Linked List 란?
* 각 노드가 `data`와 다음 노드와 이전 노드를 가리키는 `pointer`로 이루어져 있고, 한 줄로 이어져 데이터를 저장하는 자료구조이다.
* Single Linked List와 마찬가지로, 이어진 메모리 구조를 사용하는 것이 아니기 때문에, **메모리를 절약**할 수 있다는 장점이 있다. 
* 또한, 줄로 이어져 있고 다음 노드만 가르키기 때문에 삽입이나 조회가 O(n) 시간이 걸릴 수 있는 Single Linked List를 **보완**하고자 등장한 자료구조 이기 때문에, 노드 탐색이 **양방향**으로 가능하다는 장점이 있다.
  * 노드의 개수를 반을 기준으로 찾아야 하는 인덱스가 절반보다 작으면 `head`부터 탐색하면 되고, 절반보다 크다면 `tail`부터 탐색하면 된다.
* 하지만 이전 노드를 저장해야 하기 때문에 변수를 하나 더 사용한다는 점에서 메모리를 더 많이 사용한다는 단점도 존재한다.

<br>

### 👩🏻‍💻 구현 설명

* 내가 구현한 이중 연결 리스트는 다음과 같은 함수를 가진다.
  * 새로운 노드를 할당하는 함수 `getNode(int data)`
  * 리스트의 가장 앞에 데이터를 추가하는 함수 `addNode2Head(int data)`
  * 리스트의 가장 뒤에 데이터를 추가하는 함수 `addNode2Tail(int data)`
  * 리스트의 특정 순서에 데이터를 추가하는 함수 `addNode2Num(int data)`
  * 리스트에서 특정 데이터를 가지고 있는 노드의 인덱스 번호를 리턴하는 함수 `findNode(int data)`
  * 리스트에서 특정 데이터를 가지는 노드를 삭제하는 함수 `removeNode(int data, int num)`
  * 리스트를 맨 앞부터 끝까지 순회하여 데이터를 순차적으로 저장하고 노드의 개수를 리턴하는 함수 `getList(int[] output)`
  * 리스트를 맨 뒤부터 앞까지 거꾸로 순회하여 데이터를 순차적으로 저장하고 노드의 개수를 리턴하는 함수 `getReverseList(int[] output)`

<br>

![알고리즘 끄적이기-113](https://user-images.githubusercontent.com/81270604/182030608-214567c6-090f-4a79-b14b-cbf1c6b8eabe.jpg)
![알고리즘 끄적이기-114](https://user-images.githubusercontent.com/81270604/182030610-1571367c-e514-4187-81ad-9a934ce1e8aa.jpg)


<br>

**먼저 구현에 필요한 변수를 살펴보자.**
#### Node
* `public int data;` : 노드 안에 저장되는 데이터 변수
* `public Node prev;` : 노드의 이전 노드를 가리키는 변수
* `public Node next;` : 노드의 다음 노드를 가리키는 변수

#### UserSolution
* `private int nodeCnt = 0;` : 생성된 노드의 개수를 저장하기 위한 변수
* `private Node head;` : 리스트의 맨 앞의 노드를 가리키는 변수 
* `private Node tail;` : 리스트의 맨 뒤 노드를 가리키는 변수

<br>

**Methods**

#### addNode2Head(int data)
* `head`는 맨 앞 노드를 가르키고 있기 때문에 일단 head가 가르키고 있는 노드를 `nextNode` 변수에 저장한다. 
* `getNode(int data)` 함수를 통해서 노드를 새로운 노드 `newNode` 를 생성한다.
* 새롭게 생성한 노드의 `next`에 저장해 놓았던 `nextNode`를 할당한다.
* `nextNode`가 `null`이 아니라면 `nextNode.prev`를 `newNode`로 설정한다.
* 이제 맨 앞의 노드는 `newNode`이기 때문에 `head`는 `newNode`로 설정한다.
* 만약 생성된 노드가 하나라면 `tail`을 `head`로 설정한다.

<br>

#### addNode2Tail(int data)
* `nodeCnt`가 0이면 생성된 노드가 하나도 없다는 뜻이므로 `addNode2Head(int data)`를 호출한다.
* `getNode(int data)` 함수를 통해서 노드를 새로운 노드 `newNode` 를 생성한다.
* `prevNode`에는 기존에 `tail`이 가르키던 노드를 할당한다.
* `prevNode.next`에 `newNode`를 할당한다.
* `newNode.prev`에는 `prevNode`를 할당한다.
* 이제 `newNode`가 리스트의 맨 마지막 노드가 되므로, `tail`에 `newNode`를 할당한다.

<br>

#### addNode2Num(int data, int num)
* `num`의 값이 1이라면 가장 앞에 노드를 추가하라는 뜻과 같으므로 `addNode2Tail(int data)`를 호출한다.
* 순서를 저장할 변수 `count`를 1로 초기화 한 후 연결된 노드를 하나씩 반복문으로 확인한다. 
  * 현재 보고 있는 노드는 `pointNode`에 저장하여 확인하자.
* 반복문을 돌다가 `count`가 `num`보다 1 작게 된다면 `prevNode`에 현재 보고 있는 `pointNode`를 할당하고, `nextNode`에는 `pointNode.next` 노드를 할당한다.
  * 여기서 1 작은 순서를 보는 이유는 만약 `num = 2` 라면 리스트의 두번째 노드가 새롭게 삽입된 노드가 되어야 하므로, 하나 전 노드를 찾은 후 그 노드의 다음 노드를 새롭게 생성된 노드로 설정해야하기 때문이다. 
* 노드를 삽입할 순서가 리스트 내에 존재하지 않는다면 함수를 끝낸다.
* `getNode(int data)` 함수를 통해서 노드를 새로운 노드 `newNode` 를 생성한다.
* `nextNode`가 `null`이 아니라면 `nextNode.prev`에 `newNode`를 할당한다.
* `prevNode.next`에 `newNode`를 할당한다.
* `newNode.prev`에 `prevNode`를 할당한다.
* `newNode.next`에 `nextNode`를 할당하여 연결시킨다.
* `nextNode`가 null값을 가진다면 새롭게 생성된 `newNode`가 리스트의 맨 마지막 노드이므로 `tail`에 `newNode`를 할당한다.

<br>

#### findNode(int data)
* `pointNode`에 `head`를 할당한 후 반복문을 통해서 매개변수로 들어온 데이터와 같은 데이터를 가진 노드를 찾도록한다.
* 노드를 찾았다면 해당 노드의 인덱스 번호를 반환한다.

<br>

#### removeNode(int data)
* 지워야 할 노드를 찾아야 하기 때문에 반복문을 통해서 `head`노드부터 끝까지 보면서 해당 `data`를 가진 노드를 찾는다.
  * 현재 보고 있는 노드는 `pointNode`에 저장하여 확인하자.
* 지울 노드를 찾지 못하였다면 함수를 끝낸다.
* 지울 노드를 찾았는데 맨 앞의 노드라면 `head`를 `pointNode.next`로 설정하고, 연결을 끊기 위해 `pointNode.prev`와 `pointNode.next`는 `null`값으로 설정한다. 노드의 개수를 하나 줄인 뒤 함수를 끝낸다.
* 지울 노드 `pointNode`의 이전 노드를 `prevNode`에 저장한다.
* 지울 노드 `pointNode`의 다음 노드를 `nextNode`에 저장한다.
* 지울 노드의 앞 노드인 `prevNode`의 다음 노드를 `nextNode`로 설정하여 연결시켜준다.
* `nextNode`가 `null`이 아니라면 `nextNode.prev`를 `prevNode`로 설정하여 연결한다.
* 만약 삭제한 노드가 리스트의 마지막 노드였다면 `tail`에는 `prevNode`를 할당한다.
* 지운 노드의 `prev`와 `next`값을 `null`로 설정한 후에 노드의 개수를 하나 줄인 후에 함수를 종료한다. 

<br>

#### getList(int[] output)
* `head` 노드부터 시작해서 `tail`노드까지 반복문을 돌면서 노드의 데이터를 output 배열에 저장하여 저장한 데이터의 개수를 리턴한다.

<br>

#### getReverseList(int[] output)
* `tail` 노드부터 시작해서 `head`노드까지 반복문을 돌면서 노드의 데이터를 output 배열에 저장하여 저장한 데이터의 개수를 리턴한다.

<br>


### 💻 코드

구현한 Double LinkedList를 코드로 보면 다음과 같다.

```java
package etc.ss_sw_algorithm.no_5;

class Node {
    public int data;
    public Node prev;
    public Node next;

    public Node(int data) {
        this.data = data;
        this.prev = null;
        this.next = null;
    }
}

public class UserSolution {
    private final static int MAX_NODE = 10000;

    private Node[] node = new Node[MAX_NODE];
    private int nodeCnt = 0;
    private Node head;
    private Node tail;

    public Node getNode(int data) {
        node[nodeCnt] = new Node(data);
        return node[nodeCnt++];
    }

    public void init() {
        nodeCnt = 0;
        node = new Node[MAX_NODE];
        head = null;
        tail = null;
    }

    public void addNode2Head(int data) {
        Node newNode = getNode(data);

        Node nextNode = head;

        newNode.next = nextNode;

        if (nextNode != null) {
            nextNode.prev = newNode;
        }

        head = newNode;

        if (newNode.next == null) {
            tail = head;
        }
    }

    public void addNode2Tail(int data) {
        if (nodeCnt == 0) {
            addNode2Head(data);
            return;
        }

        Node newNode = getNode(data);

        Node prevNode = tail;

        prevNode.next = newNode;
        newNode.prev = prevNode;

        tail = newNode;
    }

    public void addNode2Num(int data, int num) {
        if (num == 1) {
            addNode2Head(data);
            return;
        }

        int count = 1;
        Node pointNode = head;
        Node prevNode = null;
        Node nextNode = null;

        while (pointNode != null) {
            if (count == num - 1) {
                prevNode = pointNode;
                nextNode = pointNode.next;
                break;
            }
            count++;
            pointNode = pointNode.next;
        }

        if (pointNode == null) {
            return;
        }

        Node newNode = getNode(data);

        if (nextNode != null) {
            nextNode.prev = newNode;
        }

        prevNode.next = newNode;
        newNode.prev = prevNode;
        newNode.next = nextNode;

        if (nextNode == null) {
            tail = newNode;
        }
    }

    public int findNode(int data) {
        int order = 1;

        Node pointNode = head;

        while (pointNode != null) {
            if (pointNode.data == data) {
                return order;
            }
            order++;
            pointNode = pointNode.next;
        }

        return -1;
    }

    public void removeNode(int data) {
        Node pointNode = head;
        Node prevNode;
        Node nextNode;

        while (pointNode != null) {
            if (pointNode.data == data) {
                break;
            }
            pointNode = pointNode.next;
        }

        if (pointNode == null) {
            return;
        }

        if (pointNode == head) {
            head = pointNode.next;
            pointNode.next = null;
            pointNode.prev = null;
            nodeCnt--;
            return;
        }

        nextNode = pointNode.next;
        prevNode = pointNode.prev;

        prevNode.next = nextNode;

        if (nextNode != null) {
            nextNode.prev = prevNode;
        }

        if (prevNode.next == null) {
            tail = prevNode;
        }

        pointNode.prev = null;
        pointNode.next = null;
        nodeCnt--;
    }

    public int getList(int[] output) {
        int idx = 0;

        Node pointNode = head;

        while (pointNode != null) {
            output[idx++] = pointNode.data;
            pointNode = pointNode.next;
        }

        return idx;
    }

    public int getReversedList(int[] output) {
        int idx = 0;

        Node pointNode = tail;

        while (pointNode != null) {
            output[idx++] = pointNode.data;
            pointNode = pointNode.prev;
        }

        return idx;
    }
}
```

<br>

### 💬 주절주절
단일 연결리스트를 먼저 구현해본 뒤에 이중 연결 리스트를 구현하였기 때문에 크게 어려운 부분은 없었지만, `next`에 더불어 `prev` 변수 또한 신경써줘야 하기 때문에 단일 연결리스트에 비해서는 구현이 조금 아주 조금더 복잡했다!