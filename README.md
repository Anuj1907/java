/* 
 * Enter your code here. Read input from STDIN. Print your output to STDOUT. 
 * Your class should be named CandidateCode.
*/

import java.io.*;
import java.util.*;
public class CandidateCode {
    public static void main(String args[] ) throws Exception {

    	//Write code here
        int ab[]=new int[1000]; 
        int bc[]=new int[1000];
        Scanner sc=new Scanner(System.in);
        int T=sc.nextInt();
        int count;
        for(int j=0;j<T;j++)
        {
        int N=sc.nextInt();
        for(int i=0;i<N;i++)
        {
            ab[i]=sc.nextInt();
        }
        for(int i=0;i<N;i++)
        {
            bc[i]=sc.nextInt();
        }
        count =0;
        for(int i=0;i<N-1;i++)
        {
            for(int k=i+1;k<N;k++)
            {
                if(ab[k]<ab[i])
                {
                    int y=ab[i];
                    ab[i]=ab[k];
                    ab[k]=y;
                }
            }
        }
        for(int i=0;i<N-1;i++)
        {
            for(int k=i+1;k<N;k++)
            {
                if(bc[k]<bc[i])
                {
                    int y=bc[i];
                    bc[i]=bc[k];
                    bc[k]=y;
                }
            }
        }
        for(int i=0;i<N;i++)
        {
            if(bc[i]>ab[i])
            count++;
            else
            {
                count=-1;
                break;
            }
        }
        if(count==N)
        System.out.println("WIN");
        else
        System.out.println("LOSE");
   }
    }
}
