# CSE15L LabReport 2
##### Shengqi Wu	<https://shengqiwu2004.github.io/cse15l-lab-reports/LabReport2.html>
### Part 1

Here is my code of StringServer

``````java
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    int num = 0;
    ArrayList<String> messages = new ArrayList<>();
    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            String output = "Diana(Shengqi)'s messages are \n";
            if(messages == null)
                return "There is no message";
            for(String s : messages){
                output+=s + "\n";
            }
            return output;
        } else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    messages.add(parameters[1]);
                    String output = "";
                    for(String s : messages){
                        output+=s + "\n";
                    }
                    return output;
                }
            }
            return "404 Not Found!";
        }
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

``````

<img width="437" alt="截屏2023-01-26 下午12 23 49" src="https://user-images.githubusercontent.com/114774291/214945100-f863c784-40c0-4271-a7f9-3d9cb9b2f723.png">


In this picture, it called ``main`` method and ``handleRequest`` method.First, the ``URI url`` is changed into <https://localhost://8080/add?=Hello>. Since we're adding things, the code segment inside ``if (url.getPath().contains("/add"))``is called. ``port`` is changed into ``8080`` , ``parameters[1]``was changed into "hello", a String "hello" is added into ``messages``, and then the value of output is changed.

<img width="627" alt="截屏2023-01-26 下午12 24 10" src="https://user-images.githubusercontent.com/114774291/214945122-a622cd40-ccd8-44c3-9753-567f6c05e4c8.png">


In this picture, it called ``main`` method and ``handleRequest`` method. First, the ``URI url`` is changed into <https://localhost://8080/add?=How%20are%20you>. Since we're adding things, the part inside ``if (url.getPath().contains("/add"))``is called. ``parameters[1]``was changed into "How are you", and the String "How are you" is added into ``messages`` , and then the value of output is changed.

<img width="393" alt="截屏2023-01-26 下午12 24 29" src="https://user-images.githubusercontent.com/114774291/214945150-da3b4b70-ecbb-4087-ba4e-5b91c13d020d.png">


In this picture, ``main`` method and ``handleRequest`` method are called. First, the ``URI url`` is changed into <https://localhost://8080/>. since there is only ``/``after ``8080``, we are callling the the code segment inside ``if (url.getPath().equals("/")) `` the value of ``output`` is changed.

### Part 2

I choose the bug inside ``ArrayExample.reverse()``

#### Failure-inducing input

``````java
@Test
  public void normalArrReversed(){
    int[] normalArr = {1, 2, 3, 4, 5};
    int[] reversed = {5, 4, 3, 2, 1};
    assertArrayEquals(reversed, ArrayExamples.reversed(normalArr));
  }
``````

#### No-Failure input

``````java
@Test
  public void testZeroArr(){
    int[] zeroArr = {0,0,0};
    assertArrayEquals(zeroArr, ArrayExamples.reversed(zeroArr));
  }
``````

#### output of running the tests

<img width="1008" alt="截屏2023-01-26 下午1 11 00" src="https://user-images.githubusercontent.com/114774291/214951616-385d2536-0775-47ac-bb97-c5a333c0be86.png">


#### Before- and after- code

The following is the before-code of the bug

``````java
  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
``````

Reasoning: because the funtion aims at returning an array that is the reversed ``arr``, the code segment already created a new array ``newArrary``that stores the reversed version of ``arr``; however the returning value is still arr. Thus, we should change ``return arr`` into ``return newArray``. Also, in the before-code, ``arr[i] = newArray[arr.length - i - 1]`` is giving the value of newArray to arr, which contradicts our intention to create a new arry ``newArray``. Thus, we should change it into ``newArray[arr.length - i - 1] = arr[i];``.

Thus, the following is the after-code of the bug

``````java
  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[arr.length - i - 1] = arr[i];
    }
    return newArray;
  }
``````

### Part 3

I learned how to make Web Server in my own computer. By implement ``SearchEngine.java`` and ``StringServer.java``, I gained a preliminay understanding of implementing web server . Also I learned how to use terminal to run ``JUnit``, and how to write testCases. I saw the different symptoms corresponding to various bugs. Furthermore, I also learned to fork a repository and download the code to the computer from ``github``.
