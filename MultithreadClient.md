```java
import java.net.*;
import java.io.*;


public class MultiThreadedClient_1
{
    public static void main(String[] args) throws Exception
      {
         try
		 {
            Socket s = new Socket("127.0.0.1", 0000);
            BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
            DataOutputStream out = new DataOutputStream(s.getOutputStream());
            DataInputStream in = new DataInputStream(s.getInputStream());
            String msg = " ", servermsg = " ";
            while(! msg.equals("byte"))
			{
              System.out.println("Enter a Number :");
              msg = br.readLine();
              out.writeUTF(msg);
              out.flush();
              servermsg = in.readUTF();
              System.out.println(servermsg);
            }
            s.close();
		 }
        catch {Exception e)
			{
             System.out.println(e);				
			}
			
		}
}

	  
			
```
