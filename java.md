# Java

## LeetCode

### String

```java
str.charAt(int);
str.toCharArray(); // char[]
str.chars(); // IntStream
str.trim(); // remove start+end whitespace
str.replace(char1, char2); // Replace All
str.replaceAll(strPattern, strValue); // Replace All
str.split("//s+"); // split by repeating whitespace

String.valueOf(char[]); // char array -> String
String.valueOf(char);   // one char -> String
String.join(delimiter, collectionOfStrings);
Character.isWhitespace(int a);
```

### Array

```java
// Print
Arrays.toString(array);
Arrays.deepToString(matrix);
// Convert
Arrays.asList(array);
Arrays.stream(array);
Arrays.copyOf(array, newLength);
Arrays.copyOfRange(array, from, to);
System.arraycopy(original, 0, target, 0, original.length);
// Mutate
Arrays.sort(array);
Arrays.sort(array, Collections.reverseOrder());
Arrays.sort(array, from, to); // sub-array sort
// Compare
Arrays.equals(array1, array2);
Arrays.mismatch(array1, array2);  // index of first mismatch
Arrays.binarySearch(array, value);// index of first found


// Mutate
Collections.addAll(collection, array);
Collections.sort(collection);
```

### Collection

```java
// TBD
```
