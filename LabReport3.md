# Part 1 - Bugs
ArrayExamples.java `reverseInPlace` method

Failure Inducing Input:
```
@Test 
  public void test2ReverseInPlace(){
    int[] input2 = {2,4};
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[]{4,2}, input2);
  }
```
Non-Failure Inducing Input:
```
@Test 
  public void test2ReverseInPlace(){
    int[] input2 = {4};
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[]{4}, input2);
  }
```
Symptoms:

Failure Inducing Input:
![Image](https://github.com/AKalakota23/cse15l-lab-reports/blob/371db1532f8edb130955129f20b3163beb978a0c/Screenshot%202023-11-04%20at%203.35.26%20PM.png)

Non-Failure Inducing Input:
![Image](https://github.com/AKalakota23/cse15l-lab-reports/blob/53189bab61e7ca62d77f139810257549f97939c0/Screenshot%202023-11-04%20at%203.38.24%20PM.png)

Bugged Code:
```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

Fixed Code:
```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length / 2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1]; 
      arr[arr.length-i-1] = temp;
    }
    
  }
```
This fix addresses the issue because it ensures each element is swapped without being overwritten through the use of a temp integer. The first element is swapped with the last element. The second element is swapped with the last minus 1 and so on. We do this until we reach the midpoint.  
