# Lab Report 3 - Bugs and Commands (Week 5)

## Part 1 - Bugs

The bug I chose was the bug in `ArrayExamples.java`, specifically in the `reversed(int arr)` method. This method is supposed to take an integer array and return a new array with the elements in reversed order. The code for the method is shown below.

```
    # code block
    static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length]; 
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
```

  }


1) A failure-inducing input for the buggy program, as a JUnit test and any associated code:
   ```
   # code block
   @Test
   public void testReversedLR(){
    int[] input1 = {1,2,3,4,5};
    assertArrayEquals(new int[]{5,4,3,2,1}, ArrayExamples.reversed(input1));
   }
   ```
2) An input that doesn't induce a failure, as a JUnit test and any associated code 
   ```
   # code block
   @Test
   public void testReversedLR2(){
    int[] input1 = {};
    assertArrayEquals(new int[]{}, ArrayExamples.reversed(input1));
   }
   ```
   
   
