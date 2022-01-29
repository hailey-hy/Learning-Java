### 1. 날짜와 시간

1. Calendar
- 날짜, 시간을 표현하는 추상 클래스
- 직접 객체 표현 불가능 → 메서드를 통해 완전히 구현된 클래스의 인스턴스를 얻어야 함
    
    ```java
    Calendar cal = new Calendar(); //에러
    Calendar cal = Calendar.getInstance(); //OK, Calendar 클래스의 인스턴스를 반환하는 getInstance()메서드
    ```
    
    - GregorianCalendar
        - Calendar를 상속받은 완전 구현 클래스
        - 그레고리력 구현
- get(Calendar.MONTH)
    - 반환값이 0~11이므로 0이면 1월, 11이면 12월을 의미

### 2. 형식화 클래스

1. DecimalFormat
    - 숫자를 형식화
    - 숫자 → 텍스트: 정수, 부동소수점, 금액 등의 형식으로 표현 가능
    - 텍스트 → 숫자: 텍스트 데이터를 숫자로 쉽게 변환
    
    | 기호 | 의미 | 패턴 | 결과 |
    | --- | --- | --- | --- |
    | 0 | 10진수
    (값이 없을 때 0) | 0
    0.0
    0000.0000 | 123
    123.9
    0123.9000 |
    | # | 10진수 | #
    #.#
    ####.#### | 123
    123.9
    123.9 |
    | - | 음수 부호 | -#.# | -123.9 |
    | , | 단위 구분자 | #,### | 1,234 |
    | ‘ | 이스케이프 문자 | ‘#’#.### | #1,234 |
2. SimpleDateFormat
    
    
    | 기호 | 의미 | 보기 |
    | --- | --- | --- |
    | G | 연대(BC, AD) | AD |
    | Y | 연도 | 2006 |
    | E | 요일 | 월 |
    | a | 오전/오후 | PM |
    | z | 시간대(General Time Zone) | GMT +9:00 |
3. MessageFormat
    - 데이터를 정해진 양식에 맞게 출력할 수 있도록 함
    
    ```java
    import java.text.*;
    
    class MesssageForamtEx1{
    	public static void main(String[] args){
    		String msg = "Name: {0} \nTel: {1}";
    		Object[] arguments = {
    			"이자바", "02-123-1234"
    		};
    		String result = 
    			MessageFormat.format(msg, arguments);
    	sysout(result);
    	}
    }
    ```
    

### 3. java.time 패키지

1. 구성
    1. LocalDate: 날짜 표현
    2. LocalTime: 시간 표현
    3. LocalDateTime: 날짜 & 시간 표현
    4. ZonedDateTime: 시간대
    5. Period: 날짜 - 날짜
    6. Duration: 시간 - 시간
2. 객체 생성 방법
    - now() 사용
        - 현재 날짜와 시간을 저장하는 객체 생성
        
        ```java
        LocalDate date = LocalDate.now();
        ```
        
    - of() 사용
        - 해당 필드의 값을 순서대로 지정
        
        ```java
        LocalDate date = LocalDate.of(2022, 1, 27);
        ```