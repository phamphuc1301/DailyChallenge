# DailyChallenge
```
Power Of Two Integers
Given a positive integer which fits in a 32 bit signed integer, find if it can be expressed as A^P where P > 1 and A > 0. A and P both should be integers.
```

>Example 1:
>Input: n = 4
>Output: true (4 = 2 ^ 2)

>Example 2:
>Input: n = 11
>Output: false

>Example 3:
>Input: n = 50074
>Output: false

### Solution 1
```
   public static boolean checkPowable(int number) {
    int sqrt = (int) Math.sqrt(number);
    for(int i = 2;i<=sqrt ; i++) {
      int y = 1;
      int pow = 0;
      do {
        pow = (int) Math.pow(i, y);
        if(pow == number) {
          return true;
        }
        y++;
      } while (pow<number);
    }
    return false;
  }
```
