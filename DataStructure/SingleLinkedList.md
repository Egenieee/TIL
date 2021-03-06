# Single Linked List

### π€·π»ββοΈ Single Linked List λ?
* μ½κ² λ§ν΄ κ° λΈλκ° `data`μ λ€μ λΈλλ₯Ό κ°λ¦¬ν€λ `pointer`λ‘ μ΄λ£¨μ΄μ Έ μκ³ , ν μ€λ‘ μ΄μ΄μ Έ λ°μ΄ν°λ₯Ό μ μ₯νλ μλ£κ΅¬μ‘°μ΄λ€.
* μ΄μ΄μ§ λ©λͺ¨λ¦¬ κ΅¬μ‘°λ₯Ό μ¬μ©νλ κ²μ΄ μλκΈ° λλ¬Έμ, **λ©λͺ¨λ¦¬λ₯Ό μ μ½**ν  μ μλ€λ μ₯μ μ΄ μλ€. 
* λ°λλ‘ ν μ€λ‘ μ΄μ΄μ Έ μκ³  λ€μ λΈλλ§ κ°λ₯΄ν€κΈ° λλ¬Έμ μ½μμ΄λ μ‘°νκ° **O(n)** μκ°μ΄ κ±Έλ¦°λ€. λ°μ΄ν°κ° λ§μ κ²½μ°μ λ¨μ μ΄ λ  μλ μκ² λ€.

<br>

### π©π»βπ» κ΅¬ν μ€λͺ

* λ΄κ° κ΅¬νν μ°κ²° λ¦¬μ€νΈλ λ€μκ³Ό κ°μ ν¨μλ₯Ό κ°μ§λ€.
  * μλ‘μ΄ λΈλλ₯Ό ν λΉνλ ν¨μ `getNode(int data)`
  * λ¦¬μ€νΈμ κ°μ₯ μμ λ°μ΄ν°λ₯Ό μΆκ°νλ ν¨μ `addNode2Head(int data)`
  * λ¦¬μ€νΈμ κ°μ₯ λ€μ λ°μ΄ν°λ₯Ό μΆκ°νλ ν¨μ `addNode2Tail(int data)`
  * λ¦¬μ€νΈμ νΉμ  μμμ λ°μ΄ν°λ₯Ό μΆκ°νλ ν¨μ `addNode2Num(int data)`
  * λ¦¬μ€νΈμμ νΉμ  λ°μ΄ν°λ₯Ό κ°μ§λ λΈλλ₯Ό μ­μ νλ ν¨μ `removeNode(int data, int num)`
  * λ¦¬μ€νΈλ₯Ό λ§¨ μλΆν° λκΉμ§ μννμ¬ λ°μ΄ν°λ₯Ό μμ°¨μ μΌλ‘ μ μ₯νκ³  λΈλμ κ°μλ₯Ό λ¦¬ν΄νλ ν¨μ `getList(int[] output)`

<br>

![αα‘α―αα©αα΅αα³α· αα³αα₯α¨αα΅αα΅-111](https://user-images.githubusercontent.com/81270604/182027745-0e65dcaa-ceb8-4779-8959-c04a41aa18ac.jpg)
![αα‘α―αα©αα΅αα³α· αα³αα₯α¨αα΅αα΅-112](https://user-images.githubusercontent.com/81270604/182027406-ca4e5065-dbee-4214-9033-e4be7edc6eb3.jpg)


<br>

**λ¨Όμ  κ΅¬νμ νμν λ³μλ₯Ό μ΄ν΄λ³΄μ.**
#### Node
* `public int data;` : λΈλ μμ μ μ₯λλ λ°μ΄ν° λ³μ
* `public Node next;` : λΈλμ λ€μ λΈλλ₯Ό κ°λ¦¬ν€λ λ³μ

#### UserSolution
* `private int nodeCnt = 0;` : μμ±λ λΈλμ κ°μλ₯Ό μ μ₯νκΈ° μν λ³μ
* `private Node head;` : λ¦¬μ€νΈμ λ§¨ μμ λΈλλ₯Ό κ°λ¦¬ν€λ λ³μ 
* `private Node tail;` : λ¦¬μ€νΈμ λ§¨ λ€ λΈλλ₯Ό κ°λ¦¬ν€λ λ³μ

<br>

**Methods**

#### addNode2Head(int data)
* `head`λ λ§¨ μ λΈλλ₯Ό κ°λ₯΄ν€κ³  μκΈ° λλ¬Έμ μΌλ¨ headκ° κ°λ₯΄ν€κ³  μλ λΈλλ₯Ό `nextNode` λ³μμ μ μ₯νλ€. 
* `getNode(int data)` ν¨μλ₯Ό ν΅ν΄μ λΈλλ₯Ό μλ‘μ΄ λΈλ `newNode` λ₯Ό μμ±νλ€.
* μλ‘­κ² μμ±ν λΈλμ `next`μ μ μ₯ν΄ λμλ `nextNode`λ₯Ό ν λΉνλ€.
* μ΄μ  λ§¨ μμ λΈλλ `newNode`μ΄κΈ° λλ¬Έμ `head`λ `newNode`λ‘ μ€μ νλ€.
* λ§μ½ μμ±λ λΈλκ° νλλΌλ©΄ `tail`μ `head`λ‘ μ€μ νλ€.

<br>

#### addNode2Tail(int data)
* `nodeCnt`κ° 0μ΄λ©΄ μμ±λ λΈλκ° νλλ μλ€λ λ»μ΄λ―λ‘ `addNode2Head(int data)`λ₯Ό νΈμΆνλ€.
* `getNode(int data)` ν¨μλ₯Ό ν΅ν΄μ λΈλλ₯Ό μλ‘μ΄ λΈλ `newNode` λ₯Ό μμ±νλ€.
* `tail`μ `next`μ `newNode`λ₯Ό ν λΉνλ€.
* μ΄μ  `newNode`κ° λ¦¬μ€νΈμ λ§¨ λ§μ§λ§ λΈλκ° λλ―λ‘, `tail`μ `newNode`λ₯Ό ν λΉνλ€.

<br>

#### addNode2Num(int data, int num)
* `num`μ κ°μ΄ 1μ΄λΌλ©΄ κ°μ₯ μμ λΈλλ₯Ό μΆκ°νλΌλ λ»κ³Ό κ°μΌλ―λ‘ `addNode2Tail(int data)`λ₯Ό νΈμΆνλ€.
* μμλ₯Ό μ μ₯ν  λ³μ `count`λ₯Ό 1λ‘ μ΄κΈ°ν ν ν μ°κ²°λ λΈλλ₯Ό νλμ© λ°λ³΅λ¬ΈμΌλ‘ νμΈνλ€. 
  * νμ¬ λ³΄κ³  μλ λΈλλ `pointNode`μ μ μ₯νμ¬ νμΈνμ.
* λ°λ³΅λ¬Έμ λλ€κ° `count`κ° `num`λ³΄λ€ 1 μκ² λλ€λ©΄ `prevNode`μ νμ¬ λ³΄κ³  μλ `pointNode`λ₯Ό ν λΉνκ³ , `nextNode`μλ `pointNode.next` λΈλλ₯Ό ν λΉνλ€.
  * μ¬κΈ°μ 1 μμ μμλ₯Ό λ³΄λ μ΄μ λ λ§μ½ `num = 2` λΌλ©΄ λ¦¬μ€νΈμ λλ²μ§Έ λΈλκ° μλ‘­κ² μ½μλ λΈλκ° λμ΄μΌ νλ―λ‘, νλ μ  λΈλλ₯Ό μ°Ύμ ν κ·Έ λΈλμ λ€μ λΈλλ₯Ό μλ‘­κ² μμ±λ λΈλλ‘ μ€μ ν΄μΌνκΈ° λλ¬Έμ΄λ€. 
* λΈλλ₯Ό μ½μν  μμκ° λ¦¬μ€νΈ λ΄μ μ‘΄μ¬νμ§ μλλ€λ©΄ ν¨μλ₯Ό λλΈλ€.
* `getNode(int data)` ν¨μλ₯Ό ν΅ν΄μ λΈλλ₯Ό μλ‘μ΄ λΈλ `newNode` λ₯Ό μμ±νλ€.
* `prevNode.next`μ `newNode`λ₯Ό ν λΉνλ€.
* `newNode.next`μ `nextNode`λ₯Ό ν λΉνμ¬ μ°κ²°μν¨λ€.
* `nextNode`κ° nullκ°μ κ°μ§λ€λ©΄ μλ‘­κ² μμ±λ `newNode`κ° λ¦¬μ€νΈμ λ§¨ λ§μ§λ§ λΈλμ΄λ―λ‘ `tail`μ `newNode`λ₯Ό ν λΉνλ€.

<br>

#### removeNode(int data)
* μ§μμΌ ν  λΈλλ₯Ό μ°ΎμμΌ νκΈ° λλ¬Έμ λ°λ³΅λ¬Έμ ν΅ν΄μ `head`λΈλλΆν° λκΉμ§ λ³΄λ©΄μ ν΄λΉ `data`λ₯Ό κ°μ§ λΈλλ₯Ό μ°Ύλλ€.
  * νμ¬ λ³΄κ³  μλ λΈλλ `pointNode`μ μ μ₯νμ¬ νμΈνμ.
  * λ°λ³΅λ¬Έμ λλ©΄μ `if(pointNode.data == data)` μ‘°κ±΄λ¬Έμ νμΈν λ€μμ `prevNode`μλ `pointNode`λ₯Ό μ μ₯νμ. λ°λ³΅λ¬Έμ λΉ μ Έλκ°μ λ μ§μΈ λΈλμ μ  λΈλλ₯Ό μ μ₯νκΈ° μν¨μ΄λ€.
* μ§μΈ λΈλλ₯Ό μ°Ύμ§ λͺ»νμλ€λ©΄ ν¨μλ₯Ό λλΈλ€.
* μ§μΈ λΈλλ₯Ό μ°Ύμλλ° λ§¨ μμ λΈλλΌλ©΄ `head`λ₯Ό `pointNode.next`λ‘ μ€μ νκ³ , μ°κ²°μ λκΈ° μν΄ `pointNode.next`λ `null`κ°μΌλ‘ μ€μ νλ€. λΈλμ κ°μλ₯Ό νλ μ€μΈ λ€ ν¨μλ₯Ό λλΈλ€.
* μ§μΈ λΈλ `pointNode`μ λ€μ λΈλλ₯Ό `nextNode`μ μ μ₯νλ€.
* μ§μΈ λΈλμ μ λΈλμΈ `prevNode`μ λ€μ λΈλλ₯Ό `nextNode`λ‘ μ€μ νμ¬ μ°κ²°μμΌμ€λ€.
* λ§μ½ μ­μ ν λΈλκ° λ¦¬μ€νΈμ λ§μ§λ§ λΈλμλ€λ©΄ `tail`μλ `prevNode`λ₯Ό ν λΉνλ€.
* μ§μ΄ λΈλμ `next`κ°μ `null`λ‘ μ€μ ν νμ λΈλμ κ°μλ₯Ό νλ μ€μΈ νμ ν¨μλ₯Ό μ’λ£νλ€. 

<br>

#### getList(int[] output)
* `head` λΈλλΆν° μμν΄μ `tail`λΈλκΉμ§ λ°λ³΅λ¬Έμ λλ©΄μ λΈλμ λ°μ΄ν°λ₯Ό output λ°°μ΄μ μ μ₯νμ¬ μ μ₯ν λ°μ΄ν°μ κ°μλ₯Ό λ¦¬ν΄νλ€.

<br>

### π» μ½λ

κ΅¬νν LinkedListλ₯Ό μ½λλ‘ λ³΄λ©΄ λ€μκ³Ό κ°λ€.

```java
class Node {
    public int data;
    public Node next;

    public Node(int data) {
        this.data = data;
        this.next = null;
    }

    public void setNext(Node next) {
        this.next = next;
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
        head = null;
        tail = null;
        nodeCnt = 0;
        node = new Node[MAX_NODE];
    }

    public void addNode2Head(int data) {
        Node newNode = getNode(data);
        Node nextNode = head;
        newNode.setNext(nextNode);
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
        tail.next = newNode;
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

        prevNode.next = newNode;
        newNode.next = nextNode;

        if (nextNode == null) {
            tail = newNode;
        }

    }

    public void removeNode(int data) {
        Node pointNode = head;
        Node prevNode = null;
        Node nextNode;

        while (pointNode != null) {
            if (pointNode.data == data) {
                break;
            }
            prevNode = pointNode;
            pointNode = pointNode.next;
        }

        if (pointNode == null) {
            return;
        }

        if (pointNode == head) {
            head = pointNode.next;
            pointNode.next = null;
            nodeCnt--;
            return;
        }

        // μ§μΈ λΈλμ λ€μ λΈλλ₯Ό μ μ₯
        nextNode = pointNode.next;

        // μ§μΈ λΈλ μμ λΈλμ λ€μ λΈλλ₯Ό μμμ μ μ₯ν nextNode λ‘ μ€μ ν΄μ μ°κ²°
        prevNode.next = nextNode;

        // μ­μ ν λΈλκ° λ§μ§λ§ λΈλμλ€λ©΄ tailμ κ°±μ 
        if (prevNode.next == null) {
            tail = prevNode;
        }

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
}

```

<br>

### π¬ μ£Όμ μ£Όμ 
λΈλμ `next`λ§ μ°κ²°μμΌμ λλλ κ² μλλΌ λΈλκ° λ§¨ μ λΈλμΈμ§ κ°μ₯ λ λΈλμΈμ§λ κ³ λ €ν΄μΌνκΈ° λλ¬Έμ μ‘°κΈμ ν·κ°λ Έλ€. νμ§λ§ μλ£κ΅¬μ‘°μ κΈ°λ³Έμ΄ λλ μ°κ²°λ¦¬μ€νΈλ₯Ό μ§μ  λ€μ κ΅¬νν΄λ³΄λ©΄μ κΈ°μ΄λ₯Ό λ€μ λ€μ§ μ μμλ€. 