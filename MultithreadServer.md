```java
import java.net.*;
import java.io.*;


public class MultiThreadedServer
{
   public static void main(String[] args) throws Exception
   {
	   try
	   {
		   ServerSocket ss =new ServerSocket(0000);
		   int counter = 0 ;
		   System.out.println("Server Started ......");
		   while(true)
		   {
			   counter++;
			   Socket s = ss.accept();
			   System.out.println("Client " + counter + " : Connected");
			   ServerClientThread sct = new ServerClientThread(s,counter);
			   //Send Request to seperate Thread
			   sct.start();
		   }
	   }
	   catch (Exception e)
	   {
		   System.out.println(e);
	   }
   }
}

class ServerClientThread extends Thread
{
	Socket s;
	int ClientNo;
	int squarevalue;
	ServerClientThread(Socket soc, int counter)
	{
		s= soc;
		ClientNo = counter;
	}
	public void run()
	{
		try
		{
			DataOutputStream out = new DataOutputStream(s.getOutputStream());
			DataInputStream in = new DataInputStream(s.getInputStream());
			String clientmsg = " ", servermsg = "";
			while(!clientmsg.equals("byte"))
			{
				clientmsg = in.readUTF();
				System.out.println("From Client " +ClientNo+ ", the number is " + clientmsg);
				squarevalue = Integer.parseInt(clientmsg) * Integer.parseInt(clientmsg);
				servermsg = ("From Server to Client " +ClientNo+", the square of "+ clientmsg + "is" + squarevalue);
				out.writeUTF(servermsg);
				out.flush();
		    }
			s.close();
		}
		catch(Exception e)
		{
			System.out.println(e);
		}
		finally
		{
			System.out.println("Client " + ClientNo + " : Exit ");
		}
	}
}

  		
			
```
