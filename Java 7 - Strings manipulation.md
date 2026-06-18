
### 1. Capitalize the first letter of each word and convert all remaining letters to lowercase, while preserving all other characters.

```
    // input   = " a123 hello 44world   123!    @chatGPT    #2026 $cAT    dOG "
    // output  = " A123 Hello 44World   123!    @Chatgpt    #2026 $Cat    Dog "

```
```
package demo_strings;

public class A01_CapitalizeWordLettersMixedCase {
	public static void main(String[] args) {

		String str = " a123 hello 44world   123!    @chatGPT    #2026 $cAT    dOG ";
		String res = "";
		boolean f_letter = false;

		for (int i = 0; i < str.length(); i++) {
			char current_ch = str.charAt(i);

			if (!Character.isLetter(current_ch)) {
				res += current_ch;
				f_letter = true;
			} else {
				if (f_letter) {
					res += Character.toUpperCase(current_ch);
				} else {
					res += Character.toLowerCase(current_ch);
				}
				f_letter = false;
			}
		}
		System.out.println(res);
	}
}

```

### 2. Remove letters from a string

```
// input  = "a1b2c3! 45"
// output = "123! 45"

```
```
package demo_strings;

// Purpose: Remove letters from a string
public class A23_RemoveLettersFromString {
    public static void main(String[] args) {
        String str = "a1b2c3! 45";
        str = str.replaceAll("[A-Za-z]", "").trim();
        System.out.println(str);
    }
}

```

### 3. List vowels and consonants in a string

```
// input  = "  I am ^ heRe for   %% reSt # eE  of 87 my life  "

// Output = Vowels: IaeeoeeEoie
            Constants: mhRfrrStfmylf

```
```
package demo_strings;

public class A19_VowelConsonantCounter {
	public static void main(String[] args) {
		String str = "  I am ^ heRe for   %% reSt # eE  of 87 my life  ";
		str = str.replaceAll("[^A-Za-z]", "").trim();

		StringBuilder vowels = new StringBuilder();
		StringBuilder constants = new StringBuilder();

		for (char c : str.toCharArray()) {
			if ("aeiouAEIOU".contains(String.valueOf(c))) {
				vowels.append(c);
			} else {
				constants.append(c);
			}
		}

		System.out.println("Vowels: " + vowels);
		System.out.println("Constants: " + constants);
	}
}

```
### 5. Remove duplicate values except whitespaces

```
// input = "1 2 22 2 3 4 5 3 4 4 5 45 g g h h h"
// output = "1 2 22 3 4 5 45 g h "

```
```
package demo_strings;

public class A35_RemoveDuplicateTokens {
	public static void main(String[] args) {
		String str = "1 2 22 2 3 4 5 3 4 4 5 45 g g h h h";

		String[] arr = str.replaceAll("[^0-9a-z]", " ")
				.trim().split("\\s+");

		for (int i = 0; i < arr.length; i++) {
			boolean dup = false;

			for (int j = 0; j < i; j++) {
				if (arr[i].equalsIgnoreCase(arr[j])) {
					dup = true;
					break;
				}
			}

			if (!dup)
				System.out.print(arr[i] + " ");
		}
	}
}

```

### 6. Reverse a given string

```
// input  = "321@olleH"
// output = "Hello@123"
```

```
package demo_strings;

public class A13_ReverseStringBuilder {
	public static void main(String[] args) {
		String str = "321@olleH";
		StringBuilder res = new StringBuilder();

		for (int i = str.length() - 1; i >= 0; i--) {
			res.append(str.charAt(i));
		}

		System.out.println(res.toString());
	}
}





```





