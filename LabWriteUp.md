# Lab Report 3 - Bugs and Commands (Week 5)

## Part 1 - Bugs

The bug I chose was the bug in `ArrayExamples.java`, specifically in the `reversed(int arr)` method. This method is supposed to take an integer array and return a new array with the elements in reversed order.

  }


1) A failure-inducing input for the buggy program, as a JUnit test and any associated code:
   ```
   @Test
   public void testReversedLR1(){
    int[] input1 = {1,2,3,4,5};
    assertArrayEquals(new int[]{5,4,3,2,1}, ArrayExamples.reversed(input1));
   }
   ```
   
2) An input that doesn't induce a failure, as a JUnit test and any associated code 
   ```
   @Test
   public void testReversedLR2(){
    int[] input1 = {};
    assertArrayEquals(new int[]{}, ArrayExamples.reversed(input1));
   }
   ```
   
3) The symptom, as the output of running the tests

![Image](LR3SS1.png)
![Image](LR3SS2.png)

The screenshots show the output for the two tests made in the first two parts. It shows 4 tests run because the new tests were added to the `ArrayTests.java` file, which already included 2 tests. 

4) The bug, as the before-and-after code change required to fix it


Buggy Code:

    ```
    static int[] reversed(int[] arr) {
        int[] newArray = new int[arr.length]; 
        for(int i = 0; i < arr.length; i += 1) {
          arr[i] = newArray[arr.length - i - 1];
        }
    return arr;
    }
    ```
    
Fixed Code:
   
    ```
    static int[] reversed(int[] arr) {
        int[] newArray = new int[arr.length]; //5
        for(int i = 0; i < arr.length; i += 1) {
          newArray[i] = arr[arr.length - i - 1];
        }
    return newArray;
    }
    ```
The fix addresses the code because in the buggy code, the program would change the values of     the original array rather than the new one. Because of this, it would overwrite the values, making the original values inaccessible later. The code would also replace the values of the original array with the values from the new, empty array. The fixed code changes it so that the new array, starting at index 0, is given the value of the last index in the old array. As the index of the new array increases, the index of the old array dereases, thus reversing the order of the array. The fixed code also returns the new array, rather than the original one, which was as the program intended.


## Part 2 - Researching Commands
1) The `-name` option for the `find` command can search for a file by name and return the absoulate path.

```
find technical/ -name '*.txt'
```
Output: 

![image](LR3SS3.png)

The code finds all files in the `technical` directory that ends in `.txt`. This can be useful when searching for all of the files of a certain type ( in this case, finding all text files in the directory ).

2) 
```
find technical/ -name pmed.0020075.txt
```
Output:

![image](LR3SS4.png)

The code finds the absolute path of a file named `pmed.0020075.txt` in the `technical` directory. This can be useful if you know the name of a file but don't know the location. It will return the absolute path, showing the directories leading to the file. 







