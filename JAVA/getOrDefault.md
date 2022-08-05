# Map - getOrDefualt란?

### getOrDefault
Java 8에서 추가된 Collection API 함수들 중 일부이다.

* V getOrDefault(Object Key, Object defaultValue)
* 찾는 key가 존재한다면 찾는 key의 value를 반환하고 없거나 null이면 default 값을 반환한다.

<br>

### 사용방법
` getOrDefault(Object key, V DefaultValue) `
* key : map 요소의 키이다.
* defaultValue : 지정된 키로 매핑된 값이 없거나 null이면 반환하는 기본 값이다.

```java
import java.util.HashMap;

public class practice {
	public static void main(String arg[]) {
    
        String [] abc = { "A", "B", "C" ,"C"}; 
        HashMap<String, Integer> hm = new HashMap<>(); 
        
        for(String key : abc) {
        	hm.put(key, hm.getOrDefault(key, 0) + 1); 
        }
        System.out.println("출력 결과 : " + hm); 
        // 출력 결과 : {A=1, B=1, C=2} 
     } 
}
```

