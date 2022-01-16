### 1. 조건문

---

1. 조건문
    - 조건식과 문장을 포함하는 블럭 {}으로 구성
    - if문과 switch문 두 가지 종류가 있음
        
        
        | if | switch |
        | --- | --- |
        | if(조건식-결과: true, false) {
        조건식 true 수행문장[들];
        }
        → else일 경우에는 수행하는 문장이 없음 | switch(int 수식-결과: byte, short, char, int){
        case 숫자값 :
        int 수식이 숫자값 동일할 때 수행문장[들];
        }
        int i = 10;
        switch(i){
        case 1:
        s.o.p(”10이다”);
        
        } |
        | if(조건식-결과: true, false) {
        조건식 true 수행문장[들];
        }
        다른 표현 x
        else{
        조건식 false 수행문장[들];
        }
        cf. 조건식 true 결과 : 조건식 false 결과;
        → 조건 결과를 하나만 지정할 수 있음
         | switch(String){
        case 문자열값 :
        String 수식이 문자열값과 동일할 때 수행문장[들];
        } |
        | if(조건식1){
        조건식1 true 수행문장;
        } else if (조건식2){
        조건식 1 false이고 조건식 true 수행문장;
        }else if (조건식3){
        조건식 1,2 false이고 조건식3 true 수행문장;
        }
        ...
        else{
        모든 조건식 1,2,3,...false 수행문장;
        } | switch(int){
         case 숫자값1:
          int 변수가 숫자 1과 동일한 경우 수행문장;
        break; → 이 시점에서 switch block 수행을 중단
         case 숫자값2:
          int 변수가 숫자 2과 동일한 경우 수행문장;
        } |
        | if(조건식1){
        조건 1 만족 수행문장
        if(조건2){
        조건 1, 2 만족 수행문장
        }
        }else{
        
        }
        → 중첩 if문 |  |
2. 반복문
    
    
    | for | while | do while |
    | --- | --- | --- |
    | for(int i = 1; i ≤ 10; i ++){
    
    }
    → i가 1에서 시작하여, 1 ~ 10(포함)일때, i++를 반복 수행
    
    for (시작문장; 반복조건식; 변화식){
    반복 수행 문장 정의
    }
    →보통 유한횟수의 반복문에 사용 | int i = 1;
    while(i ≤ 10){
    s.o.p(i);
    i = i + 1;
    }
    
    int i = 1;
    while(true){
    s.o.p(i);
    i = i + 1;
    }
    → 보통 무한횟수 반복문에 사용
    
    while(키보드 변수 입력 ‘a’) {
    0번 이상 무한횟수 반복
    } | int i = 11;
    do{
    s.o.p(i);
    i = i + 1;
    } while(i ≤ 10);
    → 1번 이상 수행 |
    | for(int i = 1; i ≤ 5; i ++){
     for(int j = 1; j ≤ 10; j++){
    반복문장
     }
    }
    
     |  |  |
    - 향상된 for 문
        - for (타입 변수명 : 배열 또는 컬렉션) { 반복할 문장 }
        
        ```java
        int[] arr = {10, 20, 30, 40, 50}
        
        for(int tmp : arr) {
        System.out.println(tmp);
        }
        ```
        
    - break
        1. switch 블록 내에서 사용되면 블록을 무시하고 블록 다음 문장으로 이동
        2. 반복문 블록 내에서 사용되면 반복을 중단하고 반복문 블록 다음 문장으로 이동
    - countinue
        1. 반복문 블록 내부에서 사용되면 반복일시 생략하고 반복문 블록 처음 문장으로 이동. 나머지 반복 계속 수행