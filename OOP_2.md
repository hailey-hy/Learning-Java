### 1. μμ

---

<aside>
π‘ κΈ°μ‘΄μ ν΄λμ€λ₯Ό μ¬μ¬μ©νμ¬ μλ‘μ΄ ν΄λμ€λ₯Ό μμ±νλ κ²

</aside>

- μμλ°μ ν΄λμ€λ μμνλ ν΄λμ€μ λ³μ, λ©μλλ₯Ό μλ ν¬ν¨ν¨
- μμμ κ³μΈ΅κ΅¬μ‘°
    1. μμνλ ν΄λμ€
        - super class, μμ class, parent class, base class
    2. μμλ°λ ν΄λμ€
        - subclass, νμ class, child class, derived class
    
    ```java
    class μ¬λ {
    μ μλ€
    λ°₯λ¨Ήλ€
    μ΄λ¦ λμ΄
    }
    
    class νμ¬μ extends μ¬λ {
    μΌνλ€
    κΈμ¬λ°λ€
    κΈμ¬ λΆμ
    }
    ```
    
- **λ€μ€μμ κΈμ§**: subclassλ λ κ° μ΄μμ superclassλ₯Ό μμλ°μ μ μμ
    
    ```java
    class μ¬λ {
    μ μλ€
    λ°₯λ¨Ήλ€
    μ΄λ¦ λμ΄
    }
    
    class νμ extends μ¬λ {
    κ³΅λΆνλ€
    μ±μ λ°λ€
    νμ  μ κ³΅
    }
    
    class μ΄λ±νμ extends νμ {
    //
    }
    ```
    
    - νμμ μ¬λμ λνμ¬ subclassμ΄κ³ , μ΄λ±νμμ λνμ¬ superclassμ΄λ€.
- μμ ν΄λμ€κ° λμΌν λ³μκ° μμ κ²½μ°, μμλ°μ λ³μλ³΄λ€ μκΈ° μμ μμ μ μΈλ λ³μκ° μ°μ λ¨
- μμ ν΄λμ€κ° λμΌν static ν΄λμ€ λ³μκ° μμ  κ²½μ°, μμν΄λμ€.λ³μλͺμΌλ‘ κ΅¬λΆ

```java
// 1

class μλμ°¨ {
νΈλ€ μμ νμ¬
μ μ§νλ€ () {
//
}
νμ§νλ€
}

class μ΄μ μ {
μ΄μ νλ€(){
	μλμ°¨ car = new μλμ°¨();
car.μ μ§νλ€();
}
}

//2

class μ¬λ {
λ°₯λ¨Ήλ€
}

class μ΄μ μ extends μ¬λ{
μ΄μ νλ€(){}
}
```

- λ€λ₯Έ ν΄λμ€μ μ μλ λ³μλ λ©μλλ₯Ό μ¬μ©ν΄μΌ ν  κ²½μ°
    1. μ΄μ μλ μ¬λμ΄λ€ (~ is a κ΄κ³)
        
        β λ€λ₯Έ ν΄λμ€λ₯Ό μμλ°μ μ¬μ©
        
    2. μ΄μ μλ μλμ°¨λ₯Ό μμ νλ€ (has a relationship κ΄κ³)
        
        β κ°μ²΄ μμ±ν΄ μ¬μ©
        

```java
class A //extends Object//
```

- λͺ¨λ  classλ classμ μμμ μλ Objectλ₯Ό μμλ°κ³  μλ μν
- μμ κ³μΈ΅λμ μ΅μμμλ Object ν΄λμ€κ° μμΉ

### 2. λ©μλ μ€λ²λΌμ΄λ©

---

1. λ©μλ μ€λ²λΌμ΄λ©
    
    <aside>
    π‘ μ‘°μ ν΄λμ€λ‘λΆν° μμλ°μ λ©μλμ λ΄μ©μ λ³κ²½νλ κ²
    
    </aside>
    
    - μ‘°κ±΄
        - μ‘°μ ν΄λμ€μ λ©μλμ μ΄λ¦μ΄ κ°μμΌ ν¨
        - λ§€κ°λ³μκ° κ°μμΌ ν¨
        - λ°ννμμ΄ κ°μμΌ ν¨
    - subclassμ μλ λ©μλλ₯Ό μ°μ 
    - μμ ν΄λμ€μ μ μλ λ΄μ©μ νμ ν΄λμ€μ λ§μΆ€
    - μ£Όμν  μ 
        - μ κ·Ό μ μ΄μλ μ‘°μ ν΄λμ€μ λ©μλλ³΄λ€ μ’μ λ²μλ‘ λ³κ²½ν  μ μλ€.
        - μ‘°μ ν΄λμ€μ λ©μλλ³΄λ€ λ§μ μμ μμΈλ₯Ό μ μΈν  μ μλ€.
        - μΈμ€ν΄μ€ λ©μλλ₯Ό static λ©μλλ‘, λλ λ°λλ‘ λ³κ²½ν  μ μλ€.
    
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
    a1.toString(); // -> A ν΄λμ€ μ μ
    ```
    
2. μ°¨μ΄μ  λΉκ΅: λ©μλ μ€λ²λ‘λ©
    - 1κ°μ ν΄λμ€μ ν¬ν¨λ μ¬λ¬ λ©μλμ κ΄κ³
    - λ©μλ μ΄λ¦μ΄ κ°κ³  λ§€κ°λ³μ λ¦¬μ€νΈ(νμ, κ°μ, μμ) λ€λ₯΄κ² μ μ
    - λ¦¬ν΄νμμ΄λ modefier μ ν μμ
    - 1κ° κΈ°λ₯, λ§€κ°λ³μ λ°λΌμ λ€μνκ² μ κ³΅

### 3. thisμ super

---

1. this
    - νμ¬ λ μμ μ κ°μ²΄λ₯Ό μ°Έμ‘°νλ ν€μλ
    1. this.μΈμ€ν΄μ€λ³μ: μΈμ€ν΄μ€λ³μμ λ§€κ°λ³μ, μΈμ€ν΄μ€λ³μμ μ§μ­λ³μ μ΄λ¦ κ΅¬λΆ
    2. this([κ° μ λ¬])
        - νμ¬ ν΄λμ€μ λ€λ₯Έ μμ±μλ₯Ό νΈμΆ
        - μμ±μ λ΄λΆμμ μ²« λ¬Έμ₯μ΄μ΄μΌ ν¨
2. super
    - μμ ν΄λμ€μ κ°μ²΄λ₯Ό μ°Έμ‘°νλ ν€μλ
    1. super.μμμΈμ€ν΄μ€λ³μ: μμ, νμ λμΌλͺ μΈμ€ν΄μ€λ³μ κ΅¬λΆ
    2. super.μμλ©μλ(): μμ, νμ λμΌλͺ λ©μλ(overriding) κ΅¬λΆ
    3. super(): λ§€κ°λ³μ μλ super classμ μμ±μλ₯Ό νΈμΆ
        - μμ±μ μ²«λ¬Έμ₯μ μλ μ μλ¨
    4. super([κ° μ λ¬])
        - λ§€κ°λ³μ μλ super classμ μμ±μ νΈμΆ
        - μμ±μ μ²«λ¬Έμ₯ λͺμμ  μ μ
        - μ‘°μ ν΄λμ€μ λ©€λ² λ³μλ μ‘°μμ μμ±μμ μν΄ μ΄κΈ°νλλλ‘ ν΄μΌ ν¨

```java
class A extends Objects{
	int i;
	A(){
		super();//μμ±μ μ²«λ¬Έμ₯μ μλμ μλ¨
		System.out.println("A μμ±μ νΈμΆ");
		i = 10;
	}
}

class B extends A{
	int j;
	B(){
		super();//μμ±μ μ²«λ¬Έμ₯μ μλμ μλ¨
		System.out.println("B μμ±μ νΈμΆ");
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

// μ€ν μμ: Object()μμ±μ -> A()μμ±μ -> B()μμ±μ
//μΆλ ₯ μμ: 1. Aμμ±μ νΈμΆ 2. Bμμ±μ νΈμΆ 3. 100 μΆλ ₯ 4. 10 μΆλ ₯
/
```

|  | stack | heap |
| --- | --- | --- |
| 1 | b1:  | 100: Objectκ°μ²΄:[11κ° λ©μλ]
β
200: A κ°μ²΄ [int i;]
β
300: B κ°μ²΄ [int j = 100;] |

### 4. packageμ import

---

1. Package
    - μ μ
        
        <aside>
        π‘ ν΄λμ€μ λ¬Άμ
        
        </aside>
        
    - ν΄λμ€ λλ μΈν°νμ΄μ€λ₯Ό ν¬ν¨μν¬ μ μμ
    - μ μΈ λ°©λ²
        
        ```java
        package ν¨ν€μ§λͺ;
        ```
        
    - λͺ¨λ  ν΄λμ€λ λ°λμ νλμ ν¨ν€μ§μ ν¬ν¨
    - μλ°μμ κΈ°λ³Έμ μΌλ‘ μ κ³΅νλ unnamed packageλ‘ ν¨ν€μ§ μ μΈ μλ΅ κ°λ₯
2. Import
    
    <aside>
    π‘ μ»΄νμΌλ¬μκ² μμ€νμΌμ μ¬μ©λ ν΄λμ€μ ν¨ν€μ§μ λν μ λ³΄λ₯Ό μ κ³΅ν¨
    
    </aside>
    
    - μ μΈ λ°©λ²
        
        ```java
        packageλ¬Έ
        import ν¨ν€μ§λͺ.ν΄λμ€λͺ;
        import ν¨ν€μ§λͺ.*;
        class μ μΈ
        ```
        
    - μλ import
        1. java.lang ν¨ν€μ§ ν΄λμ€ μ¬μ© (String / Integer / math, Object, ...) : λΌμ΄λΈλ¬λ¦¬
        2. νμ¬ νμΌκ³Ό κ°μ ν¨ν€μ§μ μμ±λ ν΄λμ€ μ¬μ© : μ¬μ©μ μ μ

### 5. μ μ΄μ modifier

---

|  | μ κ·Ό μ μ΄μ | class | λ³μ | λ©μλ | μμ±μ |
| --- | --- | --- | --- | --- | --- |
| μ κ·Όμ ν | public | O | O | O | O |
|  | protected | X | O | O | O |
|  | private | X | O | O | O |
| νμ©λ°©λ² | static | X | O | O | X |
|  | final | O | O | O | X |
|  | abstract | O | X | O | X |
1. μ κ·Ό μ μ΄μ 
    - μ κ·Ό: νμ¬ ν΄λμ€μ λ³μ, λ©μλ, μμ±μλ₯Ό μ΄μ©ν  μ μλ λ€λ₯Έ ν΄λμ€κ° λκ΅¬μΈμ§ κ²°μ νλ κ²
        1. private
            - λ³μλ₯Ό μ μΈν ν΄λμ€ λ΄λΆμμλ§ λ³μλ₯Ό μ¬μ© κ°λ₯
            - μνΈ, λ³΄μμ μν΄ μΈλΆμ κ³΅κ°νμ§ μμ
        2. no modifier (=default)
            - λ³μκ° μ μΈλ ν΄λμ€μ κ°μ ν¨ν€μ§ λ΄λΆμ μλ λ€λ₯Έ ν΄λμ€μμλ§ μ¬μ© κ°λ₯
        3. protected
            - λ³μκ° μ μΈλ ν΄λμ€μ κ°μ ν¨ν€μ§ λ΄λΆμ μλ λ€λ₯Έ ν΄λμ€μμλ§ μ¬μ© κ°λ₯ + λ€λ₯Έ ν¨ν€μ§μ μμλ°μ νμ ν΄λμ€μμλ μ¬μ©
        4. public
            - λͺ¨λ  ν¨ν€μ§μ ν΄λμ€μμ μ¬μ© κ°λ₯
        
        ```java
        class κ³μ’{
        
        String code = "010-2222-3333";
        private int pw = 1111;
        μκΈ(){...}
        μΆκΈ(){...}
        public μνΈλ³κ²½(){pw = xxx; ...}
        
        }
        
        class Test{
        ...main(){
        κ³μ’ acc = new κ³μ’();
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
    1. static λ³μ
        - λͺ¨λ  μΈμ€ν΄μ€μ κ³΅ν΅μ μΌλ‘ μ¬μ©λλ ν΄λμ€ λ³μ
        - μΈμ€ν΄μ€λ₯Ό μμ±νμ§ μκ³ λ μ¬μ© κ°λ₯
        - ν΄λμ€κ° λ©λͺ¨λ¦¬μ λ‘λλ  λ μμ±
    2. static λ©μλ
        - static λ³μλ₯Ό μ¬μ©νλ λ©μλλ₯Ό λ§λ¦ β Non Static (μΈμ€ν΄μ€) λ³μ μ¬μ© λΆκ°
        - =ν΄λμ€ λ©μλ
    3. singleton νμ κ°μ²΄ νμ©
        - main λ©μλμ μ€νλ  νΉμ  κ°μ²΄ 1κ°λ§ μ¬μ©νκΈ°
        - λμΌ db, λμΌ λ€νΈμν¬ κ³΅μ  νμ
        - λ©λͺ¨λ¦¬ μ μ½
        1. private μμ±μ
        2. static λ©μλ : private κ°μ²΄ μμ± μ μ
        3. μμ±λ private κ°μ²΄λ₯Ό μ μ₯ν private static νλ λ³μ μ μ
3. final
    - μλ―Έ: μ΅μ’, μμ λΆκ° β μμ, μ€λ²λΌμ΄λ© κΈμ§
    - κ΅¬μ±
        - final λ³μ: λ³μκ° 1λ² ν λΉ μ΄ν μμ  λΆκ°
        - final λ©μλ: λ©μλ μμ  λΆκ° (λ©μλ overriding κΈμ§)
        - final ν΄λμ€: ν΄λμ€ μμ λΆκ°, μμ μμ± κΈμ§, subclassing λΆκ°
            - ν΄λμ€μ ν¬ν¨λ λͺ¨λ  λ©μλκ° finalλ‘ μ·¨κΈ
4. abstract
    - μλ―Έ: λ―Έμ μ, μμ§ λ―Έκ΅¬νλ
    - κ΅¬μ±
        - abstract ν΄λμ€
            - μ΅μ 1κ°λΌλ abstract λ©μλκ° μ‘΄μ¬νλ ν΄λμ€λ₯Ό μ μν  λ μ¬μ©
            - κ°μ²΄ μμ±μ΄ λΆκ°λ₯ν¨
                
                β μμμ μ€μΌλ‘μ¨ κ°μ²΄ μ΄μ© κ°λ₯ (μμ μλ¬΄ν)
                
        - abstract λ©μλ
            - κ΅¬νλΆλ μκ³  μ μΈλΆλ§ μλ λ©μλλ₯Ό μ μν  λ μ¬μ©
            - λ©μλ overriding μλ¬΄ν
        
        β μμκ³Ό overridingμ κΈμ§νλ finalκ³Ό μ λ°λ
        
        - λ€μ€ μμ λΆκ°
5. modifierμ μ‘°ν©
    - μμ μμ
    - static final: λ³μ λμ μ μΈ
        - 1κ° λ³μλ₯Ό κ³΅μ νλ©° κ° μμ  λΆκ°ν¨
    - public static void main() :1κ° λ©μλλ‘ λκ΅¬λ νΈμΆκ°λ₯
    - public class: κ°λ₯ β private, protected classλ λΆκ°λ₯
    - final abstract class(method) β λΆκ°λ₯

### 6. λ€νμ±

---

- λ€νμ±μ μλ―Έ
    
    <aside>
    π‘ μ¬λ¬ κ°μ§ ννλ₯Ό κ°μ§ μ μλ λ₯λ ₯
    μ‘°μ ν΄λμ€ νμμ μ°Έμ‘°λ³μλ‘ μμν΄λμ€μ μΈμ€ν΄μ€λ₯Ό μ°Έμ‘°ν  μ μλλ‘ ν¨
    
    </aside>
    
1. λ³μμ νλ³ν
    - κΈ°λ³Έν: 8κ°μ§ νμ
        - μ‘°κ±΄
            1. boolean μ μΈ
            2. μλ νλ³ν: μ°μ°μ μλ΅ κ°λ₯
                - byte β short β int β long β float β double
                - char β int β long β float β double
            3. λͺμμ  νλ³ν (=κ°μ  νλ³ν)
    - μ°Έμ‘°ν: ν΄λμ€ νμ, λ°°μ΄ νμ
        - νΉμ±
            - κΈ°λ³Ένκ³Ό λ¬λ¦¬ stack μμ­μλ μ£Όμκ°μ μ μ₯νκ³  heap μμ­μ μ€μ  κ°μ²΄ μμ±
        - μ‘°κ±΄
            1. μμ κ΄κ³: μμκ΄κ³κ° μμΌλ©΄ μλ, λͺμμ  λͺ¨λ νλ³ν λΆκ°λ₯
            2. μλ νλ³ν
                - λΆλͺ¨ ν΄λμ€ λ³μλͺ = new μμμμ±μ();
                    
                    μλ νλ³ν μ΄νμλ λΆλͺ¨ ν΄λμ€μ μλ λ³μ, λ©μλλ§ μ¬μ© κ°λ₯
                    
                    β μ¬μ©νλ €λ©΄ λͺμμ  νλ³ν
                    
                    ```java
                    class A{}
                    class B extends A{}
                    class C extends B{}
                    class D extends C{}
                    
                    A a1 = new A(); //νλ³ν νμ μμ
                    A a2 = new B(); //λΆλͺ¨ ν΄λμ€ λ³μλͺ = new μμμμ±μ(); -> μλ νλ³ν
                    A a3 = new C(); //μλ νλ³ν
                    C c1 = new D(); // "
                    A a4 = new D(); // "
                    a4 = a2; //BνμμΌλ‘ μλ νλ³ν
                    
                    B b1 = new A(); //νλ³ν λΆκ°λ₯ (μ€ν μ€λ₯)
                    B b2 = new C(); //μμκ΄κ³κ° μμΌλ―λ‘ νλ³ν λΆκ°λ₯ (μ»΄νμΌ μ€λ₯)
                    
                    ```
                    
            3. λͺμμ  νλ³ν (= κ°μ μ  νλ³ν)
                - νλ³ν μ°μ°μ νμ
                - μλ νλ³ν λμλ€κ° λ€μ μλμ μμ νμμΌλ‘ μ¬λ³νμ μν¨
                - λͺμμ  νλ³ν μ΄ν λΆλͺ¨ ν΄λμ€ + μμ ν΄λμ€ ν¬ν¨μΌλ‘ λ°λ
                
                ```java
                class A{ int i = 10; A(){super();}}
                class B extends A{ int j = 20; B(){super();}}
                
                A a2 = new B(); //Aλ‘ λ°λκΈ° λλ¬Έμ A ν΄λμ€μ λ§΄λ²λ§ μ¬μ© κ°λ₯ //1
                a2.i //κ°λ₯
                a2.j //λΆκ°λ₯
                B b2 = (B)a2; //μ΅μ΄ κ°μ²΄ μμ± νμμΌλ‘ λ°κΏ => λͺμμ  νλ³ν
                b2.i //κ°λ₯
                b2.j //κ°λ₯
                
                B a2 = new B(); //μκΈ° μμ μ νμμ΄λ―λ‘ νλ³ν νμ μμ //2
                a2.i //κ°λ₯
                a2.j //κ°λ₯
                ```
                
                | λ©λͺ¨λ¦¬ κ΅¬μ‘° | stack | heap |
                | --- | --- | --- |
                | 1 | a2 (β A (μλ Bμλ€κ° Aλ‘ νλ³ν)) | Object[] β
                A[i = 10]β
                B[j = 20]  |
                | 2 | b2 (β B ((a2μ κ°μ²΄ μμ­μ κ°λ¦¬ν΄)) |  |
            4. instanceof μ°μ°μ
                - μ°Έμ‘°λ³μκ° μ°Έμ‘°νκ³  μλ μΈμ€ν΄μ€μ μ€μ  νμμ μμλ³΄λ μ°μ°μ
                - instanceof κ²°κ³Όλ‘ trueλ₯Ό μ»μλ€λ©΄ μ°Έμ‘°λ³μκ° κ²μ¬ν νμμΌλ‘ νλ³νμ΄ κ°λ₯
            5. λ€νμ± νν
                - μ¬λ¬κ°μ§ μμ ν΄λμ€ κ°μ²΄λ€μ 1κ°μ μμ ν΄λμ€ νμμΌλ‘ ν΅μΌ
                    - λ°°μ΄
                        - λ°μ΄ν°νμ [] λ°°μ΄λ³μλͺ = new λ°μ΄ν°νμ [κΈΈμ΄];
                            
                            β λμΌ νμ λ°μ΄ν°λ₯Ό μ¬λ¬κ° μ μ₯νλ λ³μ
                            
                        
                        ```java
                        A [] arr = new A[4];
                        arr[0] = new A();
                        arr[1] = new B();
                        arr[2] = new B();
                        arr[3] = new B();
                        ```
                        
                    - λ©μλ
                        - λ©μλ λ§€κ°λ³μμ μ¬λ¬κ°μ§ λ€μν κ°μ²΄λ₯Ό (μμ μ€ μμ ν΄λμ€λ‘)μ λ¬
                        
                        ```java
                        class Test {
                        
                        }
                        ```
                        

### 7. μΈν°νμ΄μ€

---

- μ°Έμ‘°ν λ³μμ νλ (νΉμν ν΄λμ€)
    - μ°Έμ‘°ν λ³μ: μ€μ κ°μ heap μμ­μ μ μ₯λλ λ³μ
- μΈν°νμ΄μ€ μ½λ μμ

```java
interface νμ {
	//[public abstract μλ΅]
	μ μ¬λ¨Ήλ€();
	κ³΅λΆνλ€();
}

interface κ΅μ§μ {
	//[public abstract μλ΅]
	μΌνλ€();
	μ μ¬λ¨Ήλ€();
}

class μ‘°κ΅ implements νμ, κ΅μ§μ { //νμ μΈν°νμ΄μ€λ₯Ό κ΅¬ννλ€
//λ μΈν°νμ΄μ€μμ μμλ°μ λ©μλ μ€λ²λΌμ΄λ© νμ
	μ μ¬λ¨Ήλ€(){} //λ©μλλ₯Ό μ€λ³΅ μμλ°μμΌλ νλ²λ§ μ€λ²λΌμ΄λ©νλ©΄ λ¬Έμ  X
	κ³΅λΆνλ€(){}
	μΌνλ€(){}
}

μ‘°κ΅ s = new μ‘°κ΅();
s.κ³΅λΆνλ€();
s.μΌνλ€();
s.μ μ¬λ¨Ήλ€();

νμ st = new νμ(); // μ€λ₯

νμ s2 = new μ‘°κ΅(); // μ‘°κ΅μμ μ€λ²λΌμ΄λ©ν λ©μλ(μΈν°νμ΄μ€λ κ΅¬ν λΆκ°λ₯μ΄κΈ° λλ¬Έ)λ§ μ¬μ© κ°λ₯
s2.κ³΅λΆνλ€();
s2.μΌνλ€(); //λΆκ°λ₯
s2.μ μ¬λ¨Ήλ€()

κ΅μ§μ s3 = new μ‘°κ΅();
s3.κ³΅λΆνλ€();//λΆκ°λ₯
s3.μΌνλ€(); 
s3.μ μ¬λ¨Ήλ€()

```

- νΉμ§
    1. public abstract μλ μ μΈ λ©μλ
    2. static final public μλ μ μΈ λ³μ
    3. λ€μ€μμ, λ€μ€κ΅¬ν κ°λ₯
    4. κ°μ²΄ μμ± λΆκ°λ₯
    5. μμ±μ νμ μμ
    6. μΆμν μ λκ° λλ€
    7. μ€μ  κ΅¬νλ κ²μ΄ μ ν μλ κΈ°λ³Έ μ€κ³λ
    8. λ―Έλ¦¬ μ ν΄μ§ κ·μΉμ λ§κ² κ΅¬ννλλ‘ νμ€μ μ μνλ λ° μ¬μ©λ¨