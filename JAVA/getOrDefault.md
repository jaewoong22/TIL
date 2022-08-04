# Map - getOrDefualt��?

### getOrDefault
Java 8���� �߰��� Collection API �Լ��� �� �Ϻ��̴�. 
* V getOrDefault(Object Key, Object defaultValue)
* ã�� key�� �����Ѵٸ� ã�� key�� value�� ��ȯ�ϰ� ���ų� null�̸� default ���� ��ȯ�Ѵ�.

<br>

### �����
``` getOrDefault(Object key, V DefaultValue) ```
* key : map ����� Ű�̴�.
* defaultValue : ������ Ű�� ���ε� ���� ���ų� null�̸� ��ȯ�ϴ� �⺻ ���̴�.

```java
import java.util.HashMap;

public class practice {
	public static void main(String arg[]) {
    
        String [] abc = { "A", "B", "C" ,"C"}; 
        HashMap<String, Integer> hm = new HashMap<>(); 
        
        for(String key : abc) {
        	hm.put(key, hm.getOrDefault(key, 0) + 1); 
        }
        System.out.println("��� ��� : " + hm); 
        // ��� ��� : {A=1, B=1, C=2} 
     } 
}
```

