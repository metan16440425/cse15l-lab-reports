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
- Bug Before Change:
  ```java
      while(index2 < list2.size()) {
      result.add(list2.get(index2));
      index1 += 1;
    }
  ```
- Bug After Change:  
 ```java
 while(index2 < list2.size()) {
      result.add(list2.get(index2));
      index2 += 1;
    }
 ```
- **The bug in the `merge` method of `ListExamples.java` was due to the incorrect increment of `index1` instead of `index2`,
  which led to an infinite loop and a heap space error when merging elements from `list2`. The fix changes the increment operation to `index2 += 1;`,
  thereby allowing the method to properly iterate through and merge elements from both lists. This adjustment ensures that the merge completes correctly, with all elements ordered as intended.**

## Part 2
- ```
  $  find ./technical -empty

  ```
- The command searches for and lists all empty files and directories within the ./technical directory, which is helpful for identifying and possibly cleaning up unused files.

- ```
  $ find ./technical/911report -empty
 
  ```
- The command searches for and lists all empty files within the ./technical/911report directory.   
Returning nothing means there are no empty files or directories in it.
The command option is found in https://www.geeksforgeeks.org/find-command-in-linux-with-examples/

- ```
  $ find . -type d
  .
  ./911report
  ./biomed
  ./government
  ./government/About_LSC
  ./government/Alcohol_Problems
  ./government/Env_Prot_Agen
  ./government/Gen_Account_Office
  ./government/Media
  ./government/Post_Rate_Comm
  ./plos
  ```
- The command lists all directories within the current directory. The output shows the directory structure starting from the current directory, including all subdirectories. This command is useful for getting an overview of the directory hierarchy. 

- ```
  $ find . -type d
  .
  ```
- The command lists all directories within the current directory. This shows nothing because there is subdirectories under ./technical/biomed. 
The command option is found from https://www.geeksforgeeks.org/find-command-in-linux-with-examples/

- ```
  $ find ./technical/911report -type f -newer ./technical/911report/chapter-1.txt

  ```
- This command searches within the ./technical/911report directory for files (-type f) that have been modified more recently than ./technical/911report/chapter-1.txt.
  This command is executed and returns no output, it means there are no files in the ./technical/911report directory that were modified after chapter-1.txt.
  This is particularly useful for identifying recent changes or updates, allowing users to focus on newly modified files for review, backup, or further processing.
-  ```
   $ find ./technical/911report -type f -newer ./technical/911report/chapter-2.txt

   ```
- This command searches within the ./technical/911report directory for files (-type f) that have been modified more recently than ./technical/911report/chapter-2.txt.
  This command is executed and returns no output, it means there are no files in the ./technical/911report directory that were modified after chapter-2.txt.
  The command option is found from https://www.geeksforgeeks.org/find-command-in-linux-with-examples/


