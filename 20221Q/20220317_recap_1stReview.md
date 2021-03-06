#1st Session Review 
범위: 자바의 신 Chapter 1 거의 다. 

1. 자바는 객체 지향적인 언어이다. 
클래스는 설계도. 객체는 클래스를 실제로 구현한 것. 
클래스는 자체로 일을 할 수 없고, 객체를 생성해야만 일을 시킬 수 있다.
객체 지향 프로그래밍의 특징 중 하나는 추상화이다. 
추상화란, 공통된 속성이나 기능을 묶어서 클래스로 정의하는 것이다. 
객체 지향을 하려면, 이렇게 클래스를 만드는 작업이 먼저 선행되어야 한다.

2. 예약어란?
객체를 생성할 때는 new 예약어를 사용하며, 생성자를 쓴다. 이때 생성자는 () 기본 생성자 뿐만 아니라 파라미터가 있는 타 생성자도 쓸 수 있음. 
final 

3. 컴파일이란?
프로그래밍 언어를 기계어로 번역하는 과정.
   (1).java  -> .class (os 구분 없이 사용 가능)
   (2)기계어로 번역.
##JVM 의 구성.

5. JIT 컴파일러.(프로그램 실행 할 때, static 컴파일 + 인터프리터 방식을 같이 씀)

실행시점에 기계어.

4. 컴파일 언어 VS 인터프리터 언어 장단점 비교. 
정적 타입 = 컴파일 언어, 동적 타입 = 인터프리터 언어일까? 

인터 프리터 언어: 소스코드를 기계어로 변환하는 과정 없이 실행. (ex. 파이썬. )
인터 프리터가 직접 고급언어를 한 줄씩 읽어가면서 runtime 상황에서 실행. 컴파일 언어에 비해 속도가 느리다. 
실행 속도는 느리지만 코드 변경 시 빌드 과정 없이 바로 실행 가능하다는 것이 장점(개발 속도는 빠름)
플랫폼에 종속적이지 않다. 

컴파일 언어: 소스코드를(프로그래밍 언어) 기계어로 변환 후에,기계에서 (ex. JVM) 기계어 코드 실행. 
소스 코드 -> 기계어 (빌드 과정)에서는 인터프리터 언어에 비해 느림. 반면 런타임 시에는 기계어로 모든 코드가 
변환되어 있어서 해석 과정 필요 없음. 빠른 실행이 가능. EX) C, C++ 

자바는 하이브리드 언어다. 

출처: https://jhkang-tech.tistory.com/136

5. 정적 언어 vs 동적 언어 
정적 타입: 컴파일 시에 타입이 결정. 변수 선언 시 앞에 타입 선언하는 언어. 
ex)C,C++,JAVA
컴파일 시에 타입에 대한 정보를 결정해서 속도/효율성 좋다. 
타입 에러로 인한 문제점을 초기에 발견 -> 타입의 안정성이 높아진다. 

동적 타입: 런타임 시에 타입이 결정. 
코드를 작성할 때, 변수 타입 명시하지 않고, 런타임에 변수 값에 따라서 타입 결정. 
유연성 높음/ 타입 에러로 인한 안정성 저하 가능성. 

EX) Python, Ruby

7. String 

   ```
   String text = "Check value"; 
   String text2 = "Check value"; 
   
   //text == text2
   //text.equals(text2) == true
   ```
   
   자바에는 constant pool 이 존재한다. 객체를 재사용하기 위해서 constant pool 이 만들어져있고, String 은 동일한 값을 갖는 객체가 있으면, 
   이미 만든 객체를 재사용한다. (둘은 같은 객체 )
   
   참고: 참조 자료형에서 == 연산자는 주소값을 비교한다 (기본 자료형에서는 값을 비교하지만.) 그래서 .equals()를 쓴다. 

   ```
   String a = "ac" //상수
   String b = new String("ac") // 
   ```
   
   String 은 new 를 통해서 객체를 생성하지 않아도 되는 유일한 타입이다. 1의 방식, 2의 방식 모두 가능하다. 
   방식 1: 위의 text 예시 처럼, 이미 만들어진 상수를 쓰기 때문에, 후에 동일한 값을 갖는 객체가 있으면 이미 만들어진 객체를 재사용한다. 
   방식 2: 값이 같은 String 객체를 생성한다고 하더라도, constant pool 의 값을 재활용 하지 않고, 별도의 객체를 생성한다. 

   처음에는 참조 자료형의 언박싱 과정과 헷갈려서 두 번째 방식이 더 시간이 많이 걸리나? 했는데, 그건 기본 자료형과 참조 자료형을 비교했을 때의 경우다. 
   여기서의 핵심은 객체를 재사용하는지/새로 생성하는지의 차이이다. 

8. String Buffer vs String Builder vs String 클래스의 차이 

String은 더하기 연산 시, 새로운 객체를 생성하고 기존 객체를 버린다 (gc 의 대상이다). 이는 메모리 낭비로 이어지기 때문에, 이러한 단점을 보완하려고 
String Builder 와 Buffer 가 등장했다. 

10. final은  변수, 메서드, 클래스에 모두 선언할 수 있다. 
*ch13에 나옴.
final 은 상속과 관련된 예약어이다. 

(1) 기본 자료형의 final 선언 

- 메서드: 클래스를 final 로 선언하는 것과 비슷한 경우다. 더 이상 overriding 할 수 없다. 다른 개발자가 메서드를 덮어 쓰는 것을 막기 위해. 
- 클래스: 클래스 객체를 생성하고, 선언된 메서드를 사용하는 건 상관 없지만. final 로 선언된 클래스는 타 클래스가 상속 받을 수 없다. 
더 이상 확장해서는 안 되는 클래스, 누가 상속받아서 변경해서는 안 되는 클래스가 있을 때 final 로 선언하자.
- 변수: 변수는 메서드, 클래스와는 조금 다르다. 더 이상 바꿀 수 없다는 의미. 수정될 수 없기 때문에 초기화 값이 필수다.
인스턴스, static(클래스) 변수를 final 로 선언한다면, 선언과 함께 값을 지정해야 한다. 그래야 변수 생성과 동시에 초기화가 되고 
컴파일 시 에러가 발생하지 않는다.


- 매개변수나 지역 변수는, 반드시 선언할 때 초기화 할 필요는 없다. 매개 변수는 이미 초기화가 되어서 넘어 왔고, 지역 변수는 메소드를 선언하는 
중괄호 내에서만 참조되기 때문에 변경할 일이 없다. 다만 값을 다시 할당하면 컴파일 에러. final 은 변하지 않는 값에서만 쓰자. 
- 
(2) 참조 자료형의 final 선언 
기본 자료형과 마찬가지로, 참조 잘형도 두 번 이상 값을 할당하거나 새로 생성자를 사용해서 초기화 할 수 없다. 
하지만 객체 안의 인스턴스/클래스 변수 등은 final 로 선언된 것이 아니기 때문에, 그러한 제약이 없다. 

```
public class MemberDto {
    public String name; 
    public String phone; 
    public String email; 
}
```

```
public class FinalReferenceType {
	final MemberDto dto = new MemberDto();

	public static void main(String args[]) {
		FinalReferenceType referenceType = new FinalReferenceType();
		referenceType.checkDto();
	}

	public void checkDto() {
		System.out.println(dto);
//		dto = new MemberDto(); //compile에러 - 이미 final인데 새로 생성자로 객체를 초기화 할 수는 없다. 
		dto.name = "Sangmin"; // 단 객체 내의 변수는 final 이 아니니까 재 할당 가능. 
		System.out.println(dto);

	}
}
```



12. 오버 라이딩 vs 오버 로딩 
오버 라이딩: 메소드 이름, 매개변수 타입/개수, 리턴타입 다 같아야 한다
# Overloading vs Overriding
오버 로딩: 메서드 이름 같아야 한다. 매개변수의 개수, 타입은 달라야 한다. 
리턴 값만 다르게 지정하면 오버로딩이 안된다. 매개 변수의 개수 혹은 타입이 다르다면, 리턴 값을 다르게 해도 오버로딩 가능하다. 
오버로딩 구현의 핵심은 매개변수의 개수/타입이다. 이유:  메소드의 이름과 매개변수 개수, 타입으로 구분짓기 때문이다. 

13. || 란? 
& , | : 연산자의 앞 조건식과 뒤 조건식을 둘 다 실행 시킨다. 반면, && ,  ||  : 연산자의 앞 조건식의 결과에 따라 뒤 조건식의 실행 여부를 결정한다. 이러한 논리연산자를 특별히 『쇼트-서킷』이라 한다.
    쇼트 서킷에서는 &&  앞의 boolean 값이 false 일 때, && 뒤를 굳이 실행하지 않음으로 불필요한 연산을 생략하고
    마찬가지로 || 앞의 boolean 값이 false 일 때만 뒤를 실행한다. (|| 앞쪽이 True 라면 뒤를 굳이 연산하지 않는다.)

쇼트 서킷의 장점은 1) 불필요한 코드 실행을 막음으로 작업의 연산 속도를 높일 수 있고,
2) 앞 조건의 결과에 따라 뒷쪽 조건 식의 실행 여부를 결정할 경우에도 사용할수있다.

출처: https://junior-datalist.tistory.com/214


#멘토님 리뷰 리스트

1. 인스턴스 변수와 클래스 변수의 차이

(1) 인스턴스 변수 vs 클래스 변수

인스턴스, 클래스 변수 모두 메소드 밖, 클래스 안에서 선언 된다.

클래스 변수
-(static 예약어가 있는객체가 여러번 생성되어도 static 변수는 처음에 한 번만 생성되고 동일한 클래스의
객체들에 의해서 공유가 된다. 다시 말해서 모든 객체가 하나의 값을 바라본다. B인스턴스에서 값을 변경하면, A인스턴스의 값도 바뀐다.

```
public class Webtest {
	static int sval = 123;

	public static void main(String[] args) {
		Webtest ex1 = new Webtest();
		Webtest ex2 = new Webtest();
		System.out.println(ex1.sval); // 123
		ex2.sval = 321;
		System.out.println(ex1.sval); // 321
	}
}
//출처: https://ramees.tistory.com/16
```

-GC 의 대상이 아니다. Heap area 가 GC 의 대상인데, 클래스 변수는 Method area 에 저장된다.
-현업에서 Static 은 상수 등 제한 적으로 사용 한다 (정답이 있는 것은 아니다)
-인스턴스 생성할 필요 없이 함수 내 호출이 가능하다.

```
public class Webtest {
	static int sval = 123;

	public static void main(String[] args) {
		System.out.println(sval); // 123
	}
}
```

인스턴스 변수
-객체 생성을 해야 사용 가능하다. new 로 객체가 생성 될 때마다, 매번 새로운 변수가 생성된다.
-GC의 대상이다.


```
public class Car {
    int speed;
    int distance; 
    String color;
}
```

(3) static method vs 일반 메서드?
객체를 생성하지 않고도 method를 쓸 수 있다. 단 클래스 변수만 사용 가능하다.

2. String name = "abc" vs String name = new String("abc")
   이렇게 두 가지 선언방법의 차이는?

상수풀에 "abc"가 존재하는지 확인하고 존재한다면, 새로운 객체를 생성하지 않고 이미 존재하는 것 재사용하게 됨.
String name1 = "abc", String name2 = "abc"라면, name1과 name 2의 주소는 같다. 
한번 생성하면, String 은 내용 변경이 안되기 때문에, 같은 인스턴스를 공유하게 된다. 
많은 변수가 리터럴을 통해 같은 주소를 참조할 수도 있으므로 영향을 줄 수 있는데,
String 이 immutable하기 때문에, 여러 쓰레드에서 접근해도 안전하다 (thread-safe)

반면 new 를 생성하면, 항상 새로운 인스턴스가 생성된다. 

문자열 리터럴은, 컴파일 시 클래스 파일에 저장된다. 
클래스 파일이 클래스 로더에 의해서 메모리에 올라갈 때, 리터럴의 목록에 있는 리터럴들이 JVM 내의 CONSTANT POOL (상수 저장소)에 저장된다. 

3. 접근 제어자는 각각 무엇이 있으며? 어떤 특성을 가질까요?

4. 자바 예외. 
예외 종류. 
프로그램 실행 시 발생할 수 있는 예외 발생에 대한 코드를 작성.
예외 발생으로 프로그램이 비정상적으로 종료되는 것을 막기 위해. 

(1) unchecked exception (runtime): 
컴파일 시 체크해주지 않기 때문에 unchecked 라고 불린다. 실행 시에만 예외 발생 여부를 알 수 있다. 
(2) error
자바 프로그램 밖에서 발생한 예외. 
에러는 프로세스에 영향을 미치고, 예외는 쓰레드에 영향을 미치다. 쓰레드가 상대적으로 덜 심각한 오류다. 
Out Of Memory, stackoverflow 
(3) checked exception: 

5. 컴파일러가 최적화가 없다는 가정 하에, String 변수에 +를 반복하는 로직이 왜 나쁜지에 대해서 설명해주세요. 
String은 immutale (변경 불가) 하다. 그렇기 떄문에, 한 번 생성된 string instance 가 갖고 있는 문자열은 읽어올수만 있고, 변경은 불가하다. 
예를 들어서, + 연산자를 이용해서 문자열을 결합할 떄, 인스턴스 내의 문자열이 바뀌는 게 아니라, 새로운 문자열이 담긴 string 인스턴스가 생성됨
+를 사용해서 문자열을 결합하면, 매 연산 마다 새로운 문자열을 가진 string instance 가 생성되서 메모리 공간을 차지한다. 
그렇기 때문에 결합 횟수를 줄이는 게 중요한데, 
문자열 간의 결합, 추출 등 문자열을 다루는 작업이 많이 필요할 때는 String 클래스 대신 StringBuffer 를 쓰는게 좋다. StringBuffer 인스턴스에 저장된 문자열은 변경이 가능해서, 
하나의 인스턴스 만으로 문자열을 다룰 수 있다. 