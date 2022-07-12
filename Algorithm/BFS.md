# BFS

### 🤷🏻‍♀️ BFS 란?
* 너비 우선 탐색(Breadth-first search, **BFS**)은 맹목적 탐색방법의 하나로 시작 정점을 방문한 후 시작 정점에 인접한 모든 정점들을 우선 방문하는 방법이다. 더 이상 방문하지 않은 정점이 없을 때까지 방문하지 않은 모든 정점들에 대해서도 너비 우선 검색을 적용한다. OPEN List는 큐를 사용해야만 레벨 순서대로 접근이 가능하다. _(참고 : [위키백과](https://ko.wikipedia.org/wiki/%EB%84%88%EB%B9%84_%EC%9A%B0%EC%84%A0_%ED%83%90%EC%83%89))_

<br>

### 👩🏻‍💻 알고리즘 설명
![BFS](https://user-images.githubusercontent.com/81270604/178501916-00d412f5-203c-4c9b-89f1-9c0c51e85df6.jpg)

BFS는 모든 노드를 방문하는 알고리즘이지만, 이 알고리즘을 응용한다면 우리가 필요한 면적을 구하는 알고리즘으로 사용할 수 있다. 
따라서 여기서는 `1`의 면적을 구하는 알고리즘으로 예를 들어 설명해보고자 한다. 

<br>

* 먼저 이중 for-loop을 통해서 `1`이 있는 칸을 찾는다. 여기서 부터 BFS 알고리즘이 시작되게 된다.
* 이 칸을 방문했다고 표시한다.
* 이 칸의 좌표를 `Queue`에 넣는다.
* 🔁 `Queue`가 빌 때까지 반복문을 돌린다.
    * `Queue`에서 원소를 `pop`하여 해당 칸의 좌표를 받아온다.
    * for-loop 4번을 통하여 해당 좌표의 상, 하, 좌, 우를 살펴본다.
      * 상, 하, 좌, 우 칸의 값이 `1`이고, 방문하지 않은 칸이면, 그 칸을 방문했다고 표시하고 `Queue`에 넣는다.
      * 🔁 으로 돌아가 반복한다.

해당 `Queue`가 비게 되면 하나의 구역 탐색을 마친 것이다. 

<br>

### 💻 코드
0과1로 이루어진 보드와 보드의 가로세로 값이 입력으로 들어왔을 때, `1`로 이루어진 구역의 개수를 반환하는 함수의 코드이다. 

```java
    // 칸의 좌표 (x, y)를 한 번에 묶어서 Point란 class로 묶어 Queue에 넣는 것이 편하기 때문에 다음과 같은 Point class를 만들었다.
    static class Point {
        int x;
        int y;

        public Point(int x, int y) {
            this.x = x;
            this.y = y;
        }

        public int getX() {
            return x;
        }

        public int getY() {
            return y;
        }
    }

    private static int getAreaCount(int[][] board, int n) {

        // 방문여부를 표시하기 위한 배열
        boolean[][] visited = new boolean[n][n];

        // 상하좌우 값을 계산하기 위한 배열
        int[] dx = new int[]{1, 0, -1, 0};
        int[] dy = new int[]{0, 1, 0, -1};

        // 구역의 개수를 구하기 위한 변수 
        int countOfArea = 0;

        Queue<Point> queue = new LinkedList<>();

        for (int i = 0 ; i < n; i++) {
            for (int j = 0 ; j < n; j++) {
                // 현재 보고 있는 칸이 1이 아니거나, 이미 방문한 칸이면 bfs 시작 안함
                if (board[i][j] != 1 || visited[i][j]) {
                    continue;
                }

                // bfs 시작 -> 구역의 개수 하나 증가
                countOfArea++;

                // 현재 좌표 큐에 삽입
                queue.add(new Point(i, j));

                // 방문했다고 표시
                visited[i][j] = true;

                // 하나의 연결된 구역 찾는 반복문
                while (!queue.isEmpty()) {
                    // 큐에서 칸의 좌표 하나 꺼내와서
                    Point curPoint = queue.poll();

                    // 하, 우, 상, 좌의 땅을 살펴본다.
                    for (int dir = 0; dir < 4; dir++) {
                        int nX = curPoint.getX() + dx[dir];
                        int nY = curPoint.getY() + dy[dir];

                        // nX와 nY가 보드 범위 밖으로 넘어갔다면 패스
                        if (nX < 0 || nX >= n || nY < 0 || nY >= n) {
                            continue;
                        }

                        // 방문하지 않았고, 1이 아닌 칸이라면 
                        if (visited[nX][nY] || board[nX][nY] != 1) {
                            continue;
                        }
                        
                        // 방문 표시를 하고, 큐에 넣는다.
                        visited[nX][nY] = true;
                        queue.add(new Point(nX, nY));
                    }
                }
            }
        }

        // 총 구역의 개수 반환한다. 
        return countOfArea;
    }

```

<br>

### 💬 주절주절
알고보니 쉬운 이 알고리즘 친구를 왜 이제야 제대로 공부했나 싶다.. 제대로 이해하고 넘어가면 응용한 문제들도 잘 풀 수 있을 것 같다. 이제라도 공부해서 다행(?)이라고 해야하나. 하여튼, 별로 한 건 없지만 하나의 큰 산을 넘은 느낌이어서 뿌듯하다.