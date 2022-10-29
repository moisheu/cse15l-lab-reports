# Lab Report 
## Part 1: Simplest Search   
Code:
```java
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler{
    List<String> strHold; 
    private void adder(String str){
        strHold.add(str);
    }
    private ArrayList<String> searcher(String str){
        ArrayList<String> hold = new ArrayList<String>();
        for(int i = 0; i<strHold.size(); i++){
            if(strHold.get(i).contains(str)){
                hold.add(strHold.get(i));
          }
        }
        return hold;
    }
    public String handleRequest(URI url){
        ArrayList<String> searchStrings = new ArrayList<String>();
        public String handleRequest(URI url){
             if (url.getPath().equals("/")) {
            return String.format("Number: %d", num);
        } else if (url.getPath().equals("/increment")) {
            num += 1;
            return String.format("Number incremented!");
        } else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("count")) {
                    num += Integer.parseInt(parameters[1]);
                    return String.format("Number increased by %s! It's now %d", parameters[1], num);
                }
            }
            return "404 Not Found!";
        }
    }
}

class SearchEngine{
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}


```

## Part 2: Testing 
This section will address testing within the lab3 directory.

### Test 1
**The Symptom**: 

```java  
  @Test 
  public void testSumEvensLength4() {
    int[] input1 = { 12, 13, 7, 2};
    assertEquals(EvensExample.sumEvenIndices(input1), 19);
  }
  ```
  
This test fails because it expects [15] but returns [19]

**The Bug and Connection**
```java
class EvensExample {
  static int sumEvenIndices(int[] nums) {
    int sum = 0;
    for(int i = 0; i < nums.length; i += 2) {
    // the error is here, it should be printing i 
      sum += nums[i + 1];
    }
    return sum;
  }
}
```
The error is in line 6 as due to the i incremented by 2 for each iteration, the sum should be adding the element at i instead of i+1 as it will add every odd index instead. 
Thus, when the test is run, the symptom of receiving 15 instead of 19 occurs as it is adding together 13 and 2, odd indexes 1 and 3 due to i+1, instead of 0 and 2 which would result in the expected output of 19. 

### Test 2
**The Symptom**: 

```java 
	@Test 
	public void testReverseInPlace() {
    int[] input1 = {6,3,4};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{4,3,6}, input1);
	}
```

This test fails as element [2] expects 6 but instead receives 4. 

**The Bug and Connection**
Original bug: 
```java
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
    //Error is here. arr[i] assigns the 'reversed' order int at that index however eliminates the index at arr[i] making it disappear 
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

Fix:  
```java
static void reverseInPlace(int[] arr) {
    int hold[] = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      hold[i] = arr[arr.length - i-1];
    }
  }
```

The original arr[i] assigns the 'reversed' order int at that index however eliminates the index at arr[i] making it disappear hence the symptom of a recurring value 4 instead of 6.



