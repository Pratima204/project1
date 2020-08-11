	import java.io.*;
	import java.util.*;
	import java.text.*;
	import java.math.*;
	import java.util.regex.*;
	import java.util.ArrayList;

	public class Game_of_Thrones_I{

	    public static void main(String[] args) {
			Scanner st=new Scanner(System.in);
			String string="";
			ArrayList<Integer> occur = new ArrayList<Integer>();

			String s=st.next();
			int distinct = 0 ;
			int c=0,w,j;
			boolean found=false;
			int one=0;
			int two=0;
			int length=s.length();
			char[] z=new char[s.length()];
		for(w=0;w<s.length();w++)
		z[w]=s.charAt(w);
		for(int i=0;i<w;i++)
		{
		    char ch=z[i];
		    for(j=i+1;j<w;j++)
		    {
			if(z[j]==ch)
			{
			    for(int k=j;k<(w-1);k++)
			    z[k]=z[k+1];
			    w--;
			    j=i;
			}
		    }
		}

		int[] t=new int[w];
		for(int i=0;i<w;i++)
		{
		    for(j=0,c=0;j<s.length();j++)
		    {
			if(z[i]==s.charAt(j))
			c++;
		    }
		   occur.add(c);
		   // System.out.print(z[i]+"="+occur.get(i)+",");
		}

			if(length%2==0)
			{
				for(int k=0;k<occur.size();k++)
				{
					if(occur.get(k)%2==0)
					found=true;
					else{
						found=false;
						break;
					}
				}
				if(found)System.out.println("YES");
				else System.out.println("NO");
			}else{

					for(int k=0;k<occur.size();k++)
					{
						if(occur.get(k)%2==1)
						one++;
						else{
							two++;
						}
					}
					if(one==1)System.out.println("YES");
					else System.out.println("NO");

			}
		}
	}
