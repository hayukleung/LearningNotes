# zigzag-conversion
---

题目描述

```
The string"PAYPALISHIRING"is written in a zigzag pattern on a given number of rows like this: (you may want to display this pattern in a fixed font for better legibility)

P   A   H   N
A P L S I I G
Y   I   R

And then read line by line:"PAHNAPLSIIGYIR"

Write the code that will take a string and make this conversion given a number of rows:

string convert(string text, int nRows);

convert("PAYPALISHIRING", 3)should return"PAHNAPLSIIGYIR".

```

```java
  public static String zigzag(String input, int size) {
    String output = "";
    int length = input.length();
    if (1 == size) {
      output = input;
    } else {
      for (int i = 0; i < size; i++) {
        int delta = (size - i - 1) * 2;
        int deltaReverse = (size - 1) * 2 - delta;
        deltaReverse = (0 == deltaReverse ? (size - 1) * 2 : deltaReverse);
        boolean flag = false;
        for (int j = i; j < length; j += (flag ? delta : deltaReverse)) {
          output += input.substring(j, j + 1);
          if (0 == i || size - 1 == i) {
          } else {
            flag = !flag;
          }
        }
      }
    }
    return output;
  }
```
