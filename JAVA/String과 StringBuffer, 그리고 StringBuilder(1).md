# String과 StringBuffer, 그리고 StringBuilder(1)

### String이란?
String 클래스의 가장 큰 특징은 불변(immutable)하다는 것입니다.
즉, 문자열이 할당된 메모리 공간이 절대 변하지 않습니다.

```java
// String str = new String("hello");
String str = "hello";

str = str + "java";
```

* 처음 str 변수에 "hello" 문자열을 넣었습니다.
* 이후 str 변수에 "java" 문자열을 더했습니다.
* 이 과정을 "hello" 값을 가지고 있던 str 변수가 가리키는 곳에 저장된 "hello"에 "java" 문자열을 더해 변경한 것으로 착각할 수 있습니다.
* 하지만 String 클래스의 가장 큰 특징은 불변(immutable)하다는 것입니다. 내부적으로는 아래와 같이 동작합니다.
* String 클래스의 참조 변수 str이 "hello java"라는 값을 가지고 있는 새로운 메모리 영역을 가리키게 변경됩니다.
* 처음 선언했던 "hello" 값이 할당되어 있던 메모리 영역은 Garbage로 남아있다가 GC(garbage collection)에 의해 사라지게 됩니다.
* String 클래스는 불변(immutable)하기 때문에 수정하는 시점에서 새로운 String 인스턴스가 생성됩니다.

<br>

> 요약하자면

문자열에 + 연산자 등을 사용하여 수정이 발생할 때 기존 문자열에 새로운 문자열이 추가되는 것이 아니라 새로운 문자열 객체를 만들고 그 객체를 참조하게 합니다. 
따라서 레퍼런스가 가리키고 있던 문자열이 다른 문자열로 대체되면 기존 문자열은 레퍼런스 참조가 사라진 상태(Unreachable)가 되어 GC(garbage collection)의 대상이 됩니다. 
장점으로는 아래서 설명한 String Pool에 의해 변하지 않는 문자열을 자주 읽어들이는 경우 좋은 성능을 기대할 수 있습니다. 
단점으로는 문자열 추가, 수정, 삭제 등의 연산이 빈번하게 발생하는 경우 힙(heap) 메모리에 많은 임시 가비지(Garbage)가 생성되어 힙(heap) 메모리 부족으로 성능에 치명적인 영향을 끼칠 수 있습니다. 

<br>

### String Pool이란?

```java
// 리터럴 생성 방식 일반적으로 사용하는 방식
String literalStr = "literal";
// new 키워드를 통해 인스턴스 생성 방식
String newStr = new String("literal");
```
위와 같이 두가지 생성 방법이 있습니다. 두 방식 모두 JVM 메모리 중 힙(heap) 영역에 생성이 됩니다.
하지만 리터럴 방식으로 생성을 하게 되면 "String Pool"이라는 공간에 생성이 됩니다.

```java
String str1 = "literal";
String str2 = "literal";
String str3 = "literal";
```

처음 "literal" 문자열을 넣은 String 변수를 선언했을 때 "literal"이라는 문자열을 String Pool에서 생성했기 때문에
이후 생성한 변수들을 추가적으로 생성하지 않고 똑같은 문자열(같은 레퍼런스)을 가리킵니다.

<br>
<br>

> 출처: https://woodadada16.tistory.com/31?category=939470



