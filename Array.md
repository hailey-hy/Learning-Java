### 1. 배열

<aside>
💡 같은 타입의 여러 변수를 하나의 묶음으로 다루는 것

</aside>

### 2. 배열의 사용

1. 배열 변수 선언
    
    → 배열을 다루기 위한 참조변수를 선언하는 것 (참조변수를 위한 공간)
    
    - 데이터 타입 배열 변수명 [];
    - 데이터 타입 배열 [] 변수명;
    
    ```java
    int arr [];
    int []arr;
    ```
    
2. 배열 메모리 생성
    
    → 실제 값이 저장되는 공간을 생성
    
    - 배열 변수명 = new 데이터타입[개수];
        
        → 단일 변수는 어차피 1개므로 데이터타입 개수 입력 생략
        
        → 메모리 값을 넘어선 인덱스는 오류
        
        → 음수 인덱스는 존재할 수 없음
        
3. 배열 값 할당
    - 배열 변수명[인덱스]
    - 인덱스는 0부터 시작
    
    ```java
    int arr[] = new int[5];
    arr[0] = 1;
    arr[1] = 2;
    arr[2] = 3;
    arr[3] = 4;
    arr[4] = 5;
    ```
    
4. 배열의 길이
    - 배열의 길이는 int범위의 양의 정수(0도 포함)이어야 함
    - 한 번 생성하면 길이를 변경할 수 없으므로 처음부터 길이를 넉넉히 잡아야 함
5. 배열의 복사
    
    ```java
    int[] arr = new int[5];
    int[] temp = new int[arr.length*2];
    
    for(int i = 0; i < arr.length; i++) {
    	tmp[i] = arr[i];
    
    arr= tmp;
    
    =====================================
    
    System.arraycopy(arr, 0, tmp, 0, arr.length);
    ```
    

### 3. 변수 선언 메모리 저장 구조

| stack 영역 | heap 영역 | class 영역(static) |
| --- | --- | --- |
| 생성된 변수 저장 영역
데이터가 차례대로 저장 | 데이터가 차례대로 저장되지 않음 |  |
| i: 4byte: 10
s: 4byte: 1000번지 → 2000번지 | 1000번지: “java”
2000번지: “programming” |  |
| 1. arr: null
3.  arr: 500 | 2. 500번지: [][][][][]
4. 500번지: [1][2][3][4][5] |  |

```java
int i = 10;
String s = “java”;
double d = 2.5;
int arr []; //1
arr = new int[5]; //2, 3
//new : heap 공간에 무언가 만들어주는 명령
arr[0] = 1;
arr[1] = 2;
arr[2] = 3;
arr[3] = 4;
arr[4] = 5; // 4
```

- 기본형: stack 영역에 저장되는 값이 “실제값”
- 참조형: 길이가 정해지지 않아 stack 영역에 “주소값”이 저장됨
    - String, 배열 등

### 4. 여러가지 배열

```java
1. (조건에 따라 배열의 개수가 다를 경우)
int arr []; //1
arr = new int[5]; //2, 3
arr[0] = 1;
arr[1] = 2;
arr[2] = 3;
arr[3] = 4;
arr[4] = 5; 
=> for(int i = 0; i < 5; i++) {
arr[i] =
(int)(Math.random()*100)+1;
}

2. (가장 흔함)
int arr [] = new int[5];
arr[0] = 1;
arr[1] = 2;
arr[2] = 3;
arr[3] = 4;
arr[4] = 5; 

3.
int arr[] = {1, 2, 3, 4, 5};
```

- 2차원 배열

```java
int scores[][]; //또는 int [][]scores; 또는 int []scores[];
scores = new int[3][5];
// scores.length -> 3
// scores[0].length => 5
// socres[0][0] -> int (데이터)
```

- 메모리 구조
    
    ```java
    int a [] = new int[5]; //1
    for(int i = 0; i < a.length; i++){
    	a[i] = 100; //2
    }
    
    int b [] = new int[a.length];
    System.arraycopy(a, 0, b, 0, a.length);
    
    a = new int[10] // 3 -> 기존 배열을 없애고 새로운 배열로 초기화
    
    ```
    
    | stack | heap |
    | --- | --- |
    | a:100 → 1 | 100:[100][100][100][100][100] → 2 |
    | a:500 → 3 | 500:[10개 정수 저장 배열] → 3 |
    | a:500
    b:200 | 100:[100][100][100][100][100] 
    200:[100][100][100][100][100]
    500:[0 10개 정수 저장 배열] |