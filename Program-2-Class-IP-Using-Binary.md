#To find the Class of IP Address Using_binary

```Java
import java .io.*;
import java.util.*;

public class first_using_binary
{
	public static void main(String args[])
	{
		String bin= "";
		Scanner sc = new Scanner(System.in);
		System.out.println("Enter the Ip Address: ");
		String s =sc.nextLine();
		String z = s.substring(0,s.indexOf('.'));
		int ip =Integer.parseInt(z);
		
		while(ip!=0)
		{
			int r= ip%2;
			ip = ip /2;
			if(r ==0)
			  bin= '0'+bin;
		    else
				bin = '1' + bin;
		}
		
		if(bin =="")
			bin = '0' + bin;
		    int l= 8-bin.length();
			for(i=0;i<l;i++)
			     bin = '0' + bin;
			if(bin.charAt(0) == '0')
				System.out.println("Class A");
			else if(bin.charAt(1) == '0')
				System.out.println("Class B");
			else if(bin.charAt(2) == '0')
				System.out.println("Class C");
			else if(bin.charAt(3) == '0')
				System.out.println("Class D");
            else
                System.out.println("Class E");
	}
}
```
	
