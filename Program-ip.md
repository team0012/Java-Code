# FIND OUT IP-ADDRESS OF YOUR SYSTEM

```java
import java.io.*;
import java.net.*;
public class ip
{
  public static void main(String[] args)throwsIOException
  {
     InetAddress IP = InetAddress.getLocalHost();
	 System.out.println("Host Name:" + IP.getHostName());
	 System.out.println("Host Address:" + IP.getHostAddress());
  }
}
```
