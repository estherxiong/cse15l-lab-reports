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
