# Java

## LeetCode

### String

```java
str.charAt(int);
str.toCharArray();  // char[]
str.chars();        // IntStream
str.trim();         // remove start+end whitespace
str.split("\\s+");  // split by repeating whitespace
str.replace(char1, char2);            // Replace All
str.replaceAll(strPattern, strValue); // Replace All

String.valueOf(char[]); // char array -> String
String.valueOf(char);   // one char -> String
String.join(delimiter, collectionOfStrings);

Character.toLowerCase(int c);
Character.isWhitespace(int c);
Character.isDigit(int c);
Character.isLetter(int c);
Character.isLetterOrDigit(int c);
```

### Array

```java
// Print
Arrays.toString(array);
Arrays.deepToString(matrix);
// Convert
Arrays.stream(array);
Arrays.stream(array).boxed().toList()
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
// Stack (No Exceptions)
var stack = new ArrayDeque<String>();
stack.push("A"); // add
stack.peek();    // get
stack.poll();    // remove & get
stack.iterator().next();

// Counter
var counter = new HashMap<String, Integer>();
counter.put("A", counter.getOrDefault("A", 0) + 1); // Increment
counter.put("B", counter.getOrDefault("B", 0) - 1); // Decrement
```
