# Lab Report #2
## Jason Chang / jsc008@ucsd.edu
## CSE15L / Section A01
## April 24, 2023

Below is lab report #2 - Servers and Bugs (Week 2)

# Part 1

## StringServer.java Code
```java
import java.io.IOException;
import java.net.URI;
import java.util.List;
import java.util.ArrayList;


class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    List < String > list = new ArrayList < String > ();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return toListS();
        } else if (url.getPath().equals("/add-message")) {

            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    list.add(parameters[1]);
                    return toListS();
                }
            }
        }

        return "404 Not Found!";
    }

    public String toListS() {
        String ret = "";
        for (int i = 0; i < list.size(); i++) {
            ret = ret + list.get(i) + "\n";
        }
        return ret;
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if (args.length == 0) {
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```

## /add-message Screenshots
![](https://raw.githubusercontent.com/JC01010/lab3/main/Screenshot%202023-04-19%20160450.png)

1. the `handleRequest()` and `toListS` methods are called.
2. the `handleRequest()` method takes the URI, which is `/add-message?s=hello`, and the values are `/add-message?s=hello`, which is the URI, `s`, which is the parameter,  and `hello`, which is the string that is added.
3. The `List <String> list` field changes when the `handleRequest()` method is called. It adds the string to the list.

![enter image description here](https://raw.githubusercontent.com/JC01010/lab3/main/Screenshot%202023-04-19%20160504.png)

1. the `handleRequest()` and `toListS` methods are called.
2. the `handleRequest()` method takes the URI, which is `/add-message?s=testing123`, and the values are `/add-message?s=testing123`, which is the URI, `s`, which is the parameter,  and `testing123`, which is the string that is added.
3. The `List <String> list` field changes when the `handleRequest()` method is called. It adds the string to the list.

# Part 2
## A failure-inducing bug
A failure-inducing bug for the buggy program was shown in the `averageWithoutLowest()` method:
```java
@Test
public void testMinArray1() {
	double[] input1 = { 1.0, 1.0, 1.0, 1.0 };
	double d = ArrayExamples.averageWithoutLowest(input1);
	assertEquals(1.0, d, 0.0001);
}
```

## A non-failure-inducing bug
A non-failure-inducing bug for the buggy program was shown in the `averageWithoutLowest()` method:
```java
@Test
public void testMinArray2() {
	double[] input1 = { 1.0, 2.0, 3.0 };
	double d = ArrayExamples.averageWithoutLowest(input1);
	assertEquals(2.5, d, 0.0001);
}
```
## The symptom, as the output of running the tests
![enter image description here](https://raw.githubusercontent.com/JC01010/lab3/main/Screenshot%202023-04-19%20162815.png)

## The Bug, Before and After
### Before
```java
// Averages the numbers in the array (takes the mean), but leaves out the
// lowest number when calculating. Returns 0 if there are no elements or just
// 1 element in the array
static double averageWithoutLowest(double[] arr) {
    if (arr.length < 2) {
        return 0.0;
    }
    double lowest = arr[0];
    for (double num: arr) {
        if (num < lowest) {
            lowest = num;
        }
    }
    double sum = 0;
    for (double num: arr) {
        if (num != lowest) {
            sum += num;
        }
    }
    return sum / (arr.length - 1);
}
```

### After
```java
// Averages the numbers in the array (takes the mean), but leaves out the
// lowest number when calculating. Returns 0 if there are no elements or just
// 1 element in the array
static double averageWithoutLowest(double[] arr) {
    if (arr.length < 2) {
        return 0.0;
    }
    double lowest = arr[0];
    for (double num: arr) {
        if (num < lowest) {
            lowest = num;
        }
    }
    double sum = 0;
    for (double num: arr) {
        sum += num;
    }
    return (sum - lowest) / (arr.length - 1);
}
```
The bug was originally that if there was more than one number in the array that was equal to the lowest, it did not count any of them. Instead, I replaced it with summing all the numbers, and simply subtracting the lowest number at the end.

# Part 3

Something I learned in lab in week 3 was how to use JUnit Tests. During the lab, I had trouble figuring out why the test methods were not running even though I wrote it in the `ArrayTests.java` code. However, I realized that I needed to add a `@Test` annotation to have JUnit specifically test that method in the `.java` file. This fix allowed me to write the tests needed to complete the in-class lab and Lab Report #2.
