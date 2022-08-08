# String과 StringBuffer, 그리고 StringBuilder(2)

### StringBuffer와 StringBuilder란?
String 클래스의 불변(immutable)과 반대로 변경이 가능(mutable)합니다.
즉, 문자열 연산을 할 때 인스턴스(new)를 한 번만 생성하고 메모리의 값을 변경시켜 문자열을 변경합니다.
문자열 연산 등으로 기존 객체의 공간이 부족하게 되는 경우 기존의 버퍼 크기를 늘리며 유연하게 동작합니다.

```java
// StringBuffer 생성
StringBuffer sb = new StringBuffer("stringBuffer");
sb.substring(2, 4); 문자열 추출
sb.insert(2, "추가"); // 문자열 추가
sb.delete(2, 4); // 문자열 삭제
sb.append("append"); // 문자열 이어 붙이기
sb.length(); // 문자열 길이 구하기
sb.capacity(); // 용량의 크기 구하기
sb.reverse(); // 문자열 뒤집기

// StringBuilder 생성
StrinBuilder sb1 = new StringBuilder("stringBuilder");
sb1.substring(2, 4); 문자열 추출
sb1.insert(2, "추가"); // 문자열 추가
sb1.delete(2, 4); // 문자열 삭제
sb1.append("append"); // 문자열 이어 붙이기
sb1.length(); // 문자열 길이 구하기
sb1.capacity(); // 용량의 크기 구하기
sb1.reverse(); // 문자열 뒤집기
```
(StringBuffer와 StringBuilder 생성, 사용 예시)


<br>

### StringBuffer와 StringBuilder의 차이점
> "동기화의 여부의 차이로 멀티 쓰레드 환경에서의 안정성"

StringBuffer는 각 메소드 별로 Synchonized Keyword가 존재하여, 멀티 쓰레드 환경에서도 동기화가 가능합니다.
즉, 멀티 쓰레드 환경에서의 안전성(thread-safe)을 가지고 있습니다.

StringBuilder는 동기화를 지원하지 않기 때문에 멀티 쓰레드 환경에서는 적합하지 않지만, 
동기화를 고려하지 않는 싱글 쓰레드 환경에서는 StringBuffer에 비해 연산 처리가 빠른 장점이 있습니다.

<br>

> 요약하자면

클래스|사용개발환경
-----|-----
**String**|조회가 많은 경우, 멀티 쓰레드 환경
**StringBuffer**|문자열 연산이 자주 발생하는 경우, 멀티 쓰레드 환경 <br>(동기화를 지원하기 때문에 Thread-safe 하다.)
**StringBuilder**|문자열 연산이 자주 발생하는 경우, 싱글 쓰레드이거나 동기화를 고려하지 않아도 되는 환경


<br>
<br>

> 출처: https://woodadada16.tistory.com/31?category=939470