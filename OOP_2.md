### 1. 상속

---

<aside>
💡 기존의 클래스를 재사용하여 새로운 클래스를 작성하는 것

</aside>

- 상속받은 클래스는 상속하는 클래스의 변수, 메소드를 자동 포함함
- 상속의 계층구조
    1. 상속하는 클래스
        - super class, 상위 class, parent class, base class
    2. 상속받는 클래스
        - subclass, 하위 class, child class, derived class
    
    ```java
    class 사람 {
    잠자다
    밥먹다
    이름 나이
    }
    
    class 회사원 extends 사람 {
    일하다
    급여받다
    급여 부서
    }
    ```
    
- **다중상속 금지**: subclass는 두 개 이상의 superclass를 상속받을 수 없음
    
    ```java
    class 사람 {
    잠자다
    밥먹다
    이름 나이
    }
    
    class 학생 extends 사람 {
    공부하다
    성적받다
    학점 전공
    }
    
    class 초등학생 extends 학생 {
    //
    }
    ```
    
    - 학생은 사람에 대하여 subclass이고, 초등학생에 대하여 superclass이다.
- 상속 클래스간 동일한 변수가 있을 경우, 상속받은 변수보다 자기 자신에서 선언된 변수가 우선됨
- 상속 클래스간 동일한 static 클래스 변수가 있을  경우, 상속클래스.변수명으로 구분

```java
// 1

class 자동차 {
핸들 색상 회사
전진하다 () {
//
}
후진하다
}

class 운전자 {
운전하다(){
	자동차 car = new 자동차();
car.전진하다();
}
}

//2

class 사람 {
밥먹다
}

class 운전자 extends 사람{
운전하다(){}
}
```

- 다른 클래스에 정의된 변수나 메소드를 사용해야 할 경우
    1. 운전자는 사람이다 (~ is a 관계)
        
        → 다른 클래스를 상속받아 사용
        
    2. 운전자는 자동차를 소유한다 (has a relationship 관계)
        
        → 객체 생성해 사용
        

```java
class A //extends Object//
```

- 모든 class는 class의 상위에 있는 Object를 상속받고 있는 상태
- 상속 계층도의 최상위에는 Object 클래스가 위치

### 2. 메소드 오버라이딩

---

1. 메소드 오버라이딩
    
    <aside>
    💡 조상 클래스로부터 상속받은 메서드의 내용을 변경하는 것
    
    </aside>
    
    - 조건
        - 조상 클래스의 메서드와 이름이 같아야 함
        - 매개변수가 같아야 함
        - 반환타입이 같아야 함
    - subclass에 있는 메소드를 우선
    - 상위 클래스에 정의된 내용을 하위 클래스에 맞춤
    - 주의할 점
        - 접근 제어자는 조상 클래스의 메서드보다 좁은 범위로 변경할 수 없다.
        - 조상 클래스의 메서드보다 많은 수의 예외를 선언할 수 없다.
        - 인스턴스 메서드를 static 메서드로, 또는 반대로 변경할 수 없다.
    
    ```java
    class Object{
    toString(){...x..}
    }
    
    class A{
    toString(){x+y}
    }
    
    class Test{
    ...main(){
    A a1 = new A();
    a1.toString(); // -> A 클래스 정의
    ```
    
2. 차이점 비교: 메소드 오버로딩
    - 1개의 클래스에 포함된 여러 메소드의 관계
    - 메소드 이름이 같고 매개변수 리스트(타입, 개수, 순서) 다르게 정의
    - 리턴타입이나 modefier 제한 없음
    - 1개 기능, 매개변수 따라서 다양하게 제공

### 3. this와 super

---

1. this
    - 현재 나 자신의 객체를 참조하는 키워드
    1. this.인스턴스변수: 인스턴스변수와 매개변수, 인스턴스변수와 지역변수 이름 구분
    2. this([값 전달])
        - 현재 클래스의 다른 생성자를 호출
        - 생성자 내부에서 첫 문장이어야 함
2. super
    - 상위 클래스의 객체를 참조하는 키워드
    1. super.상위인스턴스변수: 상위, 하위 동일명 인스턴스변수 구분
    2. super.상위메소드(): 상위, 하위 동일명 메소드(overriding) 구분
    3. super(): 매개변수 없는 super class의 생성자를 호출
        - 생성자 첫문장에 자동 정의됨
    4. super([값 전달])
        - 매개변수 있는 super class의 생성자 호출
        - 생성자 첫문장 명시적 정의
        - 조상 클래스의 멤버 변수는 조상의 생성자에 의해 초기화되도록 해야 함

```java
class A extends Objects{
	int i;
	A(){
		super();//생성자 첫문장에 자동정의됨
		System.out.println("A 생성자 호출");
		i = 10;
	}
}

class B extends A{
	int j;
	B(){
		super();//생성자 첫문장에 자동정의됨
		System.out.println("B 생성자 호출");
		j = 100;
	}
}

public class SuperTest {

	public static void main(String[] args) {
		B b1 = new B(); //1
		System.out.println(b1.j);
		System.out.println(b1.i);

	}

}

// 실행 순서: Object()생성자 -> A()생성자 -> B()생성자
//출력 순서: 1. A생성자 호출 2. B생성자 호출 3. 100 출력 4. 10 출력
/
```

|  | stack | heap |
| --- | --- | --- |
| 1 | b1:  | 100: Object객체:[11개 메소드]
←
200: A 객체 [int i;]
←
300: B 객체 [int j = 100;] |

### 4. package와 import

---

1. Package
    - 정의
        
        <aside>
        💡 클래스의 묶음
        
        </aside>
        
    - 클래스 또는 인터페이스를 포함시킬 수 있음
    - 선언 방법
        
        ```java
        package 패키지명;
        ```
        
    - 모든 클래스는 반드시 하나의 패키지에 포함
    - 자바에서 기본적으로 제공하는 unnamed package로 패키지 선언 생략 가능
2. Import
    
    <aside>
    💡 컴파일러에게 소스파일에 사용된 클래스의 패키지에 대한 정보를 제공함
    
    </aside>
    
    - 선언 방법
        
        ```java
        package문
        import 패키지명.클래스명;
        import 패키지명.*;
        class 선언
        ```
        
    - 자동 import
        1. java.lang 패키지 클래스 사용 (String / Integer / math, Object, ...) : 라이브러리
        2. 현재 파일과 같은 패키지에 작성된 클래스 사용 : 사용자 정의

### 5. 제어자 modifier

---

|  | 접근 제어자 | class | 변수 | 메소드 | 생성자 |
| --- | --- | --- | --- | --- | --- |
| 접근제한 | public | O | O | O | O |
|  | protected | X | O | O | O |
|  | private | X | O | O | O |
| 활용방법 | static | X | O | O | X |
|  | final | O | O | O | X |
|  | abstract | O | X | O | X |
1. 접근 제어자 
    - 접근: 현재 클래스의 변수, 메소드, 생성자를 이용할 수 있는 다른 클래스가 누구인지 결정하는 것
        1. private
            - 변수를 선언한 클래스 내부에서만 변수를 사용 가능
            - 암호, 보안을 위해 외부에 공개하지 않음
        2. no modifier (=default)
            - 변수가 선언된 클래스와 같은 패키지 내부에 있는 다른 클래스에서만 사용 가능
        3. protected
            - 변수가 선언된 클래스와 같은 패키지 내부에 있는 다른 클래스에서만 사용 가능 + 다른 패키지의 상속받은 하위 클래스에서도 사용
        4. public
            - 모든 패키지의 클래스에서 사용 가능
        
        ```java
        class 계좌{
        
        String code = "010-2222-3333";
        private int pw = 1111;
        입금(){...}
        출금(){...}
        public 암호변경(){pw = xxx; ...}
        
        }
        
        class Test{
        ...main(){
        계좌 acc = new 계좌();
        sysout(pw);
        	}
        }
        ```
        
        ```java
        package p;
        
        class A{
        private int i = 10;
        void m(){sysout(i);
        }
        
        class B{
        A a1 = new A();
        sysout(a1.i);}
        
        package q;
        
        class C{
        A a1 = new A();
        sysout(a1.i);
        }
        class D extends A{
        sysout(i);
        }
        ```
        
2. static
    1. static 변수
        - 모든 인스턴스에 공통적으로 사용되는 클래스 변수
        - 인스턴스를 생성하지 않고도 사용 가능
        - 클래스가 메모리에 로드될 때 생성
    2. static 메소드
        - static 변수를 사용하는 메소드를 만듦 → Non Static (인스턴스) 변수 사용 불가
        - =클래스 메소드
    3. singleton 타입 객체 활용
        - main 메소드에 실행될 특정 객체 1개만 사용하기
        - 동일 db, 동일 네트워크 공유 필요
        - 메모리 절약
        1. private 생성자
        2. static 메소드 : private 객체 생성 정의
        3. 생성된 private 객체를 저장한 private static 필드 변수 정의
3. final
    - 의미: 최종, 수정불가 → 상속, 오버라이딩 금지
    - 구성
        - final 변수: 변수값 1번 할당 이후 수정 불가
        - final 메소드: 메소드 수정 불가 (메소드 overriding 금지)
        - final 클래스: 클래스 상속 불가, 자식 생성 금지, subclassing 불가
            - 클래스에 포함된 모든 메소드가 final로 취급
4. abstract
    - 의미: 미정의, 아직 미구현된
    - 구성
        - abstract 클래스
            - 최소 1개라도 abstract 메소드가 존재하는 클래스를 정의할 때 사용
            - 객체 생성이 불가능함
                
                → 상속을 줌으로써 객체 이용 가능 (상속 의무화)
                
        - abstract 메소드
            - 구현부는 없고 선언부만 있는 메소드를 정의할 때 사용
            - 메소드 overriding 의무화
        
        → 상속과 overriding을 금지하는 final과 정반대
        
        - 다중 상속 불가
5. modifier의 조합
    - 순서 없음
    - static final: 변수 동시 선언
        - 1개 변수를 공유하며 값 수정 불가함
    - public static void main() :1개 메소드로 누구나 호출가능
    - public class: 가능 → private, protected class는 불가능
    - final abstract class(method) ⇒ 불가능

### 6. 다형성

---

- 다형성의 의미
    
    <aside>
    💡 여러 가지 형태를 가질 수 있는 능력
    조상 클래스 타입의 참조변수로 자손클래스의 인스턴스를 참조할 수 있도록 함
    
    </aside>
    
1. 변수의 형변환
    - 기본형: 8가지 타입
        - 조건
            1. boolean 제외
            2. 자동 형변환: 연산자 생략 가능
                - byte ⇒ short ⇒ int ⇒ long ⇒ float ⇒ double
                - char ⇒ int ⇒ long ⇒ float ⇒ double
            3. 명시적 형변환 (=강제 형변환)
    - 참조형: 클래스 타입, 배열 타입
        - 특성
            - 기본형과 달리 stack 영역에는 주소값을 저장하고 heap 영역에 실제 객체 생성
        - 조건
            1. 상속 관계: 상속관계가 없으면 자동, 명시적 모두 형변환 불가능
            2. 자동 형변환
                - 부모 클래스 변수명 = new 자식생성자();
                    
                    자동 형변환 이후에는 부모 클래스에 있는 변수, 메소드만 사용 가능
                    
                    → 사용하려면 명시적 형변환
                    
                    ```java
                    class A{}
                    class B extends A{}
                    class C extends B{}
                    class D extends C{}
                    
                    A a1 = new A(); //형변환 필요 없음
                    A a2 = new B(); //부모 클래스 변수명 = new 자식생성자(); -> 자동 형변환
                    A a3 = new C(); //자동 형변환
                    C c1 = new D(); // "
                    A a4 = new D(); // "
                    a4 = a2; //B타입으로 자동 형변환
                    
                    B b1 = new A(); //형변환 불가능 (실행 오류)
                    B b2 = new C(); //상속관계가 없으므로 형변환 불가능 (컴파일 오류)
                    
                    ```
                    
            3. 명시적 형변환 (= 강제적 형변환)
                - 형변환 연산자 필요
                - 자동 형변환 되었다가 다시 원래의 자식 타입으로 재변환을 위함
                - 명시적 형변환 이후 부모 클래스 + 자식 클래스 포함으로 바뀜
                
                ```java
                class A{ int i = 10; A(){super();}}
                class B extends A{ int j = 20; B(){super();}}
                
                A a2 = new B(); //A로 바뀌기 때문에 A 클래스의 맴버만 사용 가능 //1
                a2.i //가능
                a2.j //불가능
                B b2 = (B)a2; //최초 객체 생성 타입으로 바꿈 => 명시적 형변환
                b2.i //가능
                b2.j //가능
                
                B a2 = new B(); //자기 자신의 타입이므로 형변환 필요 없음 //2
                a2.i //가능
                a2.j //가능
                ```
                
                | 메모리 구조 | stack | heap |
                | --- | --- | --- |
                | 1 | a2 (→ A (원래 B였다가 A로 형변환)) | Object[] ←
                A[i = 10]←
                B[j = 20]  |
                | 2 | b2 (→ B ((a2의 객체 영역을 가리킴)) |  |
            4. instanceof 연산자
                - 참조변수가 참조하고 있는 인스턴스의 실제 타입을 알아보는 연산자
                - instanceof 결과로 true를 얻었다면 참조변수가 검사한 타입으로 형변환이 가능
            5. 다형성 표현
                - 여러가지 자식 클래스 객체들을 1개의 상위 클래스 타입으로 통일
                    - 배열
                        - 데이터타입 [] 배열변수명 = new 데이터타입 [길이];
                            
                            → 동일 타입 데이터를 여러개 저장하는 변수
                            
                        
                        ```java
                        A [] arr = new A[4];
                        arr[0] = new A();
                        arr[1] = new B();
                        arr[2] = new B();
                        arr[3] = new B();
                        ```
                        
                    - 메소드
                        - 메소드 매개변수에 여러가지 다양한 객체를 (상속 준 상위 클래스로)전달
                        
                        ```java
                        class Test {
                        
                        }
                        ```
                        

### 7. 인터페이스

---

- 참조형 변수의 하나 (특수한 클래스)
    - 참조형 변수: 실제값은 heap 영역에 저장되는 변수
- 인터페이스 코드 예시

```java
interface 학생 {
	//[public abstract 생략]
	점심먹다();
	공부하다();
}

interface 교직원 {
	//[public abstract 생략]
	일하다();
	점심먹다();
}

class 조교 implements 학생, 교직원 { //학생 인터페이스를 구현한다
//두 인터페이스에서 상속받은 메소드 오버라이딩 필수
	점심먹다(){} //메소드를 중복 상속받았으나 한번만 오버라이딩하면 문제 X
	공부하다(){}
	일하다(){}
}

조교 s = new 조교();
s.공부하다();
s.일하다();
s.점심먹다();

학생 st = new 학생(); // 오류

학생 s2 = new 조교(); // 조교에서 오버라이딩한 메소드(인터페이스는 구현 불가능이기 때문)만 사용 가능
s2.공부하다();
s2.일하다(); //불가능
s2.점심먹다()

교직원 s3 = new 조교();
s3.공부하다();//불가능
s3.일하다(); 
s3.점심먹다()

```

- 특징
    1. public abstract 자동 선언 메소드
    2. static final public 자동 선언 변수
    3. 다중상속, 다중구현 가능
    4. 객체 생성 불가능
    5. 생성자 필요 없음
    6. 추상화 정도가 높다
    7. 실제 구현된 것이 전혀 없는 기본 설계도
    8. 미리 정해진 규칙에 맞게 구현하도록 표준을 제시하는 데 사용됨