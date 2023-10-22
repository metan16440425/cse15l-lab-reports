# Lab Report 2
## Part 1
- **CODE** :
```java
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;
import java.util.List;

class StringHandler implements URLHandler {
    private List<String> messages = new ArrayList<>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.join("\n", messages);
        } else if (url.getPath().equals("/add-message")) {
            String query = url.getQuery();
            if (query != null && query.startsWith("s=")) {
                String message = query.substring(2);
                System.out.println("Before adding message: " + messages);
                messages.add((messages.size() + 1) + ". " + message);
                System.out.println("After adding message: " + messages);
                return String.join("\n", messages);
            } else {
                return "Invalid request. Please provide a message with ?s=<message>.";
            }
        } else {
            return "404 Not Found!";
        }
    }
}

public class StringServer {
    public static void main(String[] args) throws IOException {
        if (args.length == 0) {
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new StringHandler());
    }
}
```

- ![Image](add1.png)
- **Methods Called**: `handleRequest`
- **Relevant Arguments**: `url` with value `new URI("/add-message?s=Hello")`
- **Values of Relevant Fields**: 
  -  `messages` = `[]` (an empty list).
- **How Values Change**: 
  - The `messages` list gets updated to `["1. Hello"]`
 
- ![Image](add2.png)
- **Methods Called:** :`handleRequest`
- **Relevant Arguments:** : `url` with value `new URI("/add-message?s=How+are+you+123")`
- **Values of Relevant Fields:** :`messages` = `["1. Hello"]`
- **How Values Change:** :The `messages` list gets updated to `["1. Hello", "2. How+are+you+123"]`

## Part 2
- ![Image](private.png)

- ![Image](public.png)
  
- ![Image](login.png)

  ## Part 3
  
