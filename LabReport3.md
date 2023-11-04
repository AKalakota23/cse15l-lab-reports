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
![Image](<img width="776" alt="Screenshot 2023-11-04 at 3 35 26 PM" src="https://github.com/AKalakota23/cse15l-lab-reports/assets/122422354/73a2396c-a1f7-42a2-9a1d-3d5004436ea1">)

Non-Failure Inducing Input:
![Image](<img width="466" alt="Screenshot 2023-11-04 at 3 38 24 PM" src="https://github.com/AKalakota23/cse15l-lab-reports/assets/122422354/fa3276b7-f06a-425b-8b82-b9a14dcb96cb">)

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
