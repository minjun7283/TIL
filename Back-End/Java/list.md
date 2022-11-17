# list
```java
package chap11;

import java.util.*;

public class ListDemo {

	public static void main(String[] args) {
		String[] arr= {"사슴","호랑이","바다표범","곰"};
		
		List<String> list=Arrays.asList(arr);
		Iterator<String> it = list.iterator();
		while(it.hasNext()) {
			System.out.print(it.next()+" ");
		}
		System.out.println();
		
		list.set(1, "앵무새");
		it=list.iterator();
		while(it.hasNext()) {
			System.out.print(it.next()+" ");
		}
		System.out.println();
		Arrays.sort(arr);
		System.out.println(Arrays.toString(arr));
		Collections.sort(list);
		
		it=list.iterator();
		while(it.hasNext()) {
			System.out.print(it.next()+" ");
		}
		System.out.println();
		
	}

}
```