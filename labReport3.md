# Lab Report 3 - Symptoms and Failure-Inducing Inputs

# Part 1 - Bugs #

The bug I chose is the `reversed()` method in the `ArrayExamples.java` file\
**Original Method Code:**
```
// Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
<br />

**A failure-inducing input for the buggy program:**
```
@Test
  public void testReversedFailure() {
    int[] input3 = {1, 2, 3};
    assertArrayEquals(new int[]{3,2,1}, ArrayExamples.reversed(input3));
  }
```

**An input that doesn't induce a failure:**
```
@Test
  public void testReversedSuccess() {
    int[] input4 = {0,0,0,0};
    assertArrayEquals(new int[]{0,0,0,0}, ArrayExamples.reversed(input4));
  }
```
