1. 자바 컬렉션이란? 목록성 데이터를 처리하는 자료 구조


2. 자바 데이터의 자료 구조

(1) List (순서가 있는 목록형. 데이터 중복 o)
(2) Set (순서 중요 x. 데이터 중복 x)
(3) Queue (first in first out)
(4) key-value 가 저장되는 Map 형  (순서x. 키는 중복 허용하지 않지만 값은 중복 가능.)

3. List 인터페이스를 구현한 클래스 

(1) ArrayList: 확장된 배열이기 때문에 배열처럼 순서가 중요하다. 
(2) Vector
(3) Stack: Last in first out을 지원하기 위함. 
(4) LinkedList

4.  얕은 복사 vs 깊은 복사 

(1) 얕은 복사 
```
list2 = list; //// list2가 list의 값 뿐만 아니라, 참조 되어 있는 주소 까지 사용하겠다. 
```

위와 같이 하면, 다른 객체에 원본 객체의 주소 값을 할당하는 것이다 참조하고 있는 실제 값이 같다. 

(2) 깊은 복사 
객체의 모든 값을 복사해서 복제된 객체에 있는 값을 변경해도 원본에 영향이 없도록 할 때 (즉 실제 값은 새로운 메모리 공간에 복사하기 때문에, 실제 값이 다르다) 
arraycopy()와 같은 메서드가 그렇다.


5. 
size(): ArrayList 객체에 들어가 있는 데이터의 갯수를 가져오는 것.
length: 배열의 저장 공간 갯수 (저장 가능한. 담을 수 있는)