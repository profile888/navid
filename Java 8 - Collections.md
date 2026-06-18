### 1.  Count frequency of each character in string using HashMap  

```
// input  = "apple, banana,$$ apple,@@ orange,-- banana"
// output =
p    4
a    9
b    2
r    1
e    3
g    1
l    2
n    5
o    1

```

```
package demo_collections;

import java.util.HashMap;
import java.util.Map;

public class A06_CharacterFrequencyCounter {

	public static void main(String[] args) {
		String str = "apple, banana,$$ apple,@@ orange,-- banana";
		char[] parts = str.replaceAll("[^a-z]", "").trim().toCharArray();

		Map<Character, Integer> map = new HashMap<>();

		for (char ch : parts)
			map.put(ch, map.getOrDefault(ch, 0) + 1);

		for (char key : map.keySet())
			System.out.println(key + "    " + map.get(key));
	}
}

```

### 2. Find first repeated character that is repeating 3 times (using HashMap)

```
// input  = "kswissk"
// output = s 3
```
```
package demo_collections;

import java.util.HashMap;
import java.util.Map;

public class A11_FirstRepeatedCharacter {

	public static void main(String[] args) {
		String str = "kswissk";
		Map<Character, Integer> map = new HashMap<>();

		for (char c : str.toCharArray())
			map.put(c, map.getOrDefault(c, 0) + 1);

		for (char c : str.toCharArray()) {
		    if (map.get(c) == 3) {
		        System.out.println(c + " " + map.get(c));
		        break;
		    }
		}
	}
}

```

### 3. Reverse string while keeping special characters in place (using ArrayList)

```
// input  = "A$B#C"
// output = "C$B#A"

```

```
package demo_collections;

import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class A10_ReverseStringPreserveSpecialChars {

	public static void main(String[] args) {
		String str = "A$B#C";
		List<Character> list = new ArrayList<>();

		for (char ch : str.toCharArray())
			list.add(ch);

		List<Character> rev = new ArrayList<>(list);
		Collections.reverse(rev);

		for (int i = 0; i < list.size(); i++) {
			if (!Character.isLetter(list.get(i)))
				rev.set(i, list.get(i));
		}

		System.out.println(rev);
	}
}

```






