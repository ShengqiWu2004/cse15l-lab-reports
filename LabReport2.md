# CSE15L LabReport 2

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


In this picture, it called ``main`` method and ``handleRequest`` method.First, the ``URI url`` is changed into <https://localhost://8080/add?=Hello>. Since we're adding things, the code segment inside ``if (url.getPath().contains("/add"))``is called. ``port`` is changed into ``8080`` , ``parameters[1]``was changed into "hello", a String "hello" is added into ``messages`` , and then the value of output is changed.

<img width="627" alt="截屏2023-01-26 下午12 24 10" src="https://user-images.githubusercontent.com/114774291/214945122-a622cd40-ccd8-44c3-9753-567f6c05e4c8.png">


In this picture, it called ``main`` method and ``handleRequest`` method. First, the ``URI url`` is changed into <https://localhost://8080/add?=How%20are%20you>. Since we're adding things, the part inside ``if (url.getPath().contains("/add"))``is called. ``parameters[1]``was changed into "How are you", and the String "How are you" is added into ``messages`` , and then the value of output is changed.

<img width="393" alt="截屏2023-01-26 下午12 24 29" src="https://user-images.githubusercontent.com/114774291/214945150-da3b4b70-ecbb-4087-ba4e-5b91c13d020d.png">


In this picture, ``main`` method and ``handleRequest`` method are called. First, the ``URI url`` is changed into <https://localhost://8080/>. since there is only ``/``after ``8080``, we are callling the the code segment inside ``if (url.getPath().equals("/")) `` the value of ``output`` is changed.
