# GCD-of-n-numbers-in-java
import java.util.Scanner;
class GCDOfTwoNumbers
{
	public static void main(String[] args)
	{
		int n,x,y;
		
		
		Scanner in=new Scanner(System.in);
		System.out.println("enter size of array");
		n=in.nextInt();
	
		int[] arr=new int[n];
		for(int i=0; i<arr.length; i++)
		{
			arr[i]=in.nextInt();
		}
		x=arr[0];
		y=arr[1];
		int ans=gcd(x,y);
		
		for(int i=2;i<arr.length; i++)
		{
			ans=gcd(arr[i],ans);
		}
		System.out.println("GCD of"+n+" Numbers is ");
		System.out.println(ans);
		
	}
	
	public static int gcd(int no1,int no2)
	{
		 int divisor,dividend,remainder=1;
		
		if(no1>no2)
		{
			dividend=no1;
			divisor=no2;
		}
		else
		{
			dividend=no2;
			divisor=no1;
		}
		
		while(remainder!=0)
		{
			remainder=dividend%divisor;
			dividend=divisor;
			divisor=remainder;
		}
		return dividend;
		
	}
}
