### Daily 12: Excel Column Number
```
Given a column title as appears in an Excel sheet, return its corresponding column number.
Example:
  A -> 1
  B -> 2  
  C -> 3  
  ...
  Z -> 26  
  AA -> 27  
  AB -> 28 
  ABC -> 731
  AAAA -> 18279
```
### Solution 1 - As hell
private static Map<Character, Integer> map = new TreeMap<>();
#### Step 1
   Define map has key is Character such as "A","B"..."Z" and value is a number
   represent for the character Example A->1 , Z ->26
 ```
  public static Map<Character, Integer> init() {
    char currentChar;
    for (int i = 1; i < 27; i++) {
      currentChar = (char) (i + 64);
      map.put(currentChar, i);
    }
    return map;
  }
```
#### Step 2
  Process input String and return corresponding column number 
  ```
  public static int convertToNumber(String strColumnVal) {
    init();
    char[] arrChar = strColumnVal.toCharArray();
    int length = arrChar.length;
    int root = (int) Math.pow(26, length - 1) + map.get(arrChar[length - 1]);
    for (int i = 1; i < length - 1; i++) {
      System.out.println(map.get(arrChar[i]));
      root += map.get(arrChar[i]) * Math.pow(26, i);
    }
    return root;
  }
  ```
  ### Solution 2 - masterpiece
  ```
    public static int solution2(String strColumnVal) {
    int result = 0;
    for (int i = 0; i < strColumnVal.length(); i++) {
      result = result*26 + (int)(strColumnVal.charAt(i)-'A' +1);
    }
    return result;
  }
  ```
