# Lab Report 2 | Servers and Bug
## Part 1 | Using a Server
![Image](StringServer code.png)
![Image](sob 1.png)
![Image](sob 2.png)
## Part 2 | Examining ArrayTests.java Bug
I chose to examine the bug from testReversed() method from ArrayExamples.java 
**Failure Inducing Input**
```
 @Test
  public void testReversed() {
    int[] input2 = {3,4,5,6,7,8,9};
    assertArrayEquals(new int[]{9,8,7,6,5,4,3}, ArrayExamples.reversed(input2));
  }
```
**Successful Inducing Input**
```
@Test
  public void testReversed() {
    int[] input1 = {0};
    assertArrayEquals(new int[]{0}, ArrayExamples.reversed(input1));
```
**The Symptom**
![Image](fail.png)
*Original Code*
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
**Fixed Code**
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```
From observing the code above, we see that the symptom
