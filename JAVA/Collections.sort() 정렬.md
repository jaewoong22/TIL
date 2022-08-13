# Java 정렬방법 Collections.sort()

Java에서 정렬은 java.util.Collections 클래스의 sort() 메소드를 이용한다.
* sort()의 매개변수 타입은 List<T>로 제네릭을 받는다.
* 이 때 T는 Comparable 인터페이스를 구현해야만 한다.

##### 예제

```java
public class sort {
	
	public static void main(String[] args) {
		
		List<String> nameList = new ArrayList<>();
		
		nameList.add("Park");
		nameList.add("Choi");
		nameList.add("Kim");
		
		System.out.println("- 정렬 전" + nameList);
		
		Collections.sort(nameList);
		
		System.out.println("- 정렬 후" + nameList);
		
	}
}
```

정렬 전: [Park,Choi,Kim] <br>
<b>정렬 후: [Choi,Kim,Park]</b>

<br><br>

> 참고자료: https://wjheo.tistory.com/entry/Java-%EC%A0%95%EB%A0%AC%EB%B0%A9%EB%B2%95-Collectionssort

