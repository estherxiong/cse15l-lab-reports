# Lab Report 2 - Servers and Bugs (1/30/23)
## Part 1

Task: Write a web server `StringServer` that support the path and behavior described below. It should keep track of a single string that gets added to by incoming requests. The requests should look like this:

```/add-message?s=<string>```

Code:

```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {

    String output = "";
    public String handleRequest(URI url) {
        System.out.println("Path: " + url.getPath());
        if (url.getPath().contains("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            output+=parameters[1] + '\n';
        }
        return output;
    }
}

class StringServer {
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

### Request: `/add-message?s=hi!`

<img width="384" alt="Screenshot 2023-01-28 at 7 11 56 PM" src="https://user-images.githubusercontent.com/122568591/215305002-3d60ebd1-ec24-4235-9390-f5bd782a4fd8.png">

* The methods that are called are .getPath, .contains, .getQuery, .split
* The relevant arguments to those methods are args[0], "/add-message", "=".
* `input` is changed when the message is appended

### Request: `/add-message?s=my name is esther :-)`

<img width="476" alt="Screenshot 2023-01-28 at 7 12 23 PM" src="https://user-images.githubusercontent.com/122568591/215305003-d913c0ce-3043-40fc-9c7c-1f6605f38a00.png">

* The methods that are called are .getPath, .contains, .getQuery, .split
* The relevant arguments to those methods are args[0], "/add-message", "=".
* `input` is changed when the message is appended

## Part 2

A failure-inducing input:
```	
public void testReverseInPlace() {
int[] input1 = { 1, 2, 3 };
ArrayExamples.reverseInPlace(input1);
assertArrayEquals(new int[]{ 3, 2, 1 }, input1);
}
```

An input that doesn't induce a failure:
```
public void testReverseInPlace() {
int[] input1 = { 3 };
ArrayExamples.reverseInPlace(input1);
assertArrayEquals(new int[]{ 3 }, input1);
}
```

The symptom of the two tests:

<img width="660" alt="Screenshot 2023-01-28 at 9 40 49 PM" src="https://user-images.githubusercontent.com/122568591/215307375-9e739e54-da80-4e9d-a12d-0f289e8e9726.png">

Before(bug):
```
static void reverseInPlace(int[] arr) {
for(int i = 0; i < arr.length; i += 1) {
  arr[i] = arr[arr.length - i - 1];
}
}
```

After:
```
static void reverseInPlace(int[] arr) {
int[] temp = arr.clone();
for(int i = 0; i < arr.length; i += 1) {
  arr[i] = temp[arr.length - i - 1];
}
}
```

The fix addressed the issue of needing to create a temp array cloned from the original. That way, all the elements in the original array can be assigned correctly, using the temp array. The code with the bug lost values when assigning elements to new indices.

## Part 3

Something I learned from the labs are how to build and run a web server, as well as how to run the server using a remote computer. I also learned about paths and the various commands you can create and implement to the website. Some examples include /add-message, /count, and /increment.
