# sheet1

// الاسم:احمد حمدى ابراهيم رضوان
// id : 4

package sheet1;

import java.util.Scanner;

public class MySpecialArrayUtils {

	// *************************************methods
	public static void reverse (int[] arr) {
		int temp;
		int n = arr.length;
		for(int i=0;i< (n/2) ;i++) {
			temp = arr[i];
			arr[i] = arr[n-(i+1)];
			arr[n-(i+1)] = temp;
		}
		for(int i=0;i<arr.length;i++){
			System.out.println(arr[i]+" ");
		}
	}
	public static int[] sumEvenOdd(int[] arr) {
		int[] sum = new int[2];
		sum[0] = 0;
		sum[1] = 0;
			if(arr.length == 0) {
				sum[0] = 0;
				sum[1] = 0;
			}else {
				for(int element : arr) {
					
					if( element%2 == 0) {
						sum[0]+=element;
					}else {
						sum[1]+=element;
					}
					
			    }
			
		}
		return sum;
	}
	
	//to avoid overflow we divide each element by size of the array and then add them togther
	public static double average(int[] arr) {
		double average=0;
		double n = arr.length;
		if(arr.length == 0) {
			return 0.0;
		}else {
		for(int element : arr) {
			average += (double)element / n;
		}
		
		return average;
		}
	}
	

}



// program for transpose


package rectangular;

import java.util.Scanner;

public class matrix {

	
	// ************************** the method
	 public static void transpose(int[][] arr) {
		
		 int[][] trans = new int [arr[0].length][arr.length];
		 
		 for(int i =0 ;i< arr.length;i++) {
			 for(int j=0 ;j < arr[0].length ; j++) {
				 trans[j][i] = arr[i][j];
			 }
		 }
		 for(int i=0;i<arr[0].length;i++) {
				for(int j=0;j<arr.length;j++) {
					System.out.print(trans[i][j] + " ");
				}
				System.out.println();
			}
	 }


}


// method for sequences


package sequences;

import java.util.Scanner;

public class anotherSolu {

	
	public static void moveValuee(int[] arr,int value) {
		int i=0,j=0;
		while(i<arr.length) {
			if(arr[i] == value) {
				i++;
			}else {
				arr[j] = arr[i];
				j++;
				i++;
			}
		}
		while(j<arr.length) {
			arr[j] = value;
			j++;
		}
		for(i=0;i<arr.length;i++) {
			System.out.print(arr[i] + " ");
		}
	}
}

// program for fibonacci iterative and recursion 



package fibonacci;

import java.util.Scanner;

public class fib {

	
	//iterative method
	public static long  fibo(int n) {
		 long fib1 = 0;
		 long fib2 = 1;
		for(int i = 2;i<=n;i++) {
			// to avoid overflow use long 
			 long temp = fib1 ;
			fib1 = fib1+fib2;
			fib2 =temp;
		}
		return fib1;
	}
	
	// recursion method 
	public static long  fibonacci_nth(int n) {
		if(n == 1 ) {
			return 0;
		}else if(n == 2) {
			return 1;
		}else {
			return fibonacci_nth(n-1)+fibonacci_nth(n-2);
		}
	}
}



