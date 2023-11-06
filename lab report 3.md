# Lab Report 3
## Part 1
- **CODE** :
```java
import org.junit.Test;
import static org.junit.Assert.assertEquals;
import java.util.Arrays;
import java.util.List;

public class ListTests {
    @Test
    public void testMergeBugInduced() {
        List<String> list1 = Arrays.asList("apple");
        List<String> list2 = Arrays.asList("banana", "carrot");

        List<String> result = ListExamples.merge(list1, list2);
        List<String> expected = Arrays.asList("apple", "banana", "carrot");

        assertEquals( expected, result);
    }

```
```java
    @Test
    public void testMergeNoBugInduced() {
        List<String> list1 = Arrays.asList("apple", "banana");
        List<String> list2 = Arrays.asList();

        List<String> result = ListExamples.merge(list1, list2);
        List<String> expected = Arrays.asList("apple", "banana");

        assertEquals( expected, result);
    }
}
```
- ![Image](output.jpg)
- 
