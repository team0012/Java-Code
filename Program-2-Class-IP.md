#To find the Class of IP Address
```java
import java .io.*;
import java.util.*;

public class first1
{
	public static void main(String args[])
	{
		Scanner sc = new Scanner(System.in);
		System.out.println("Enter the Ip Address: ");
		String s =sc.nextLine();
		String z = s.substring(0,s.indexOf('.'));
		int x =Integer.parseInt(z);
		if(x>=0 && x<=128)
			System.out.println("Class A");
		else if(x>=128 && x<=192)
			System.out.println("Class B");
		else if(x>=192 && x<=224)
			System.out.println("Class C");
		else if(x>=224 && x<=240)
			System.out.println("Class D");
		else 
			System.out.println("Class E");
	}
}
```
