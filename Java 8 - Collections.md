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








