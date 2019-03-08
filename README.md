# sheet1

package sheet1;

import java.util.Scanner;

public class MySpecialArrayUtils {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		System.out.println("Enter size of the Array");
		Scanner  s = new Scanner(System.in);
		int size = s.nextInt();
		if(size <= 0) {
			System.out.println("Array is empty");
			if(size==0) {
				int[] arr = new int[0];
				int[] totalSum = sumEvenOdd(arr);
				System.out.println();
				System.out.println("sumEven "+totalSum[0] + " " +"sumOdd "+ totalSum[1]);
				
				System.out.println("The average array is ");
				System.out.println(average(arr));
			}
		}else {
			System.out.println("Enter Array Elements");
			int[] arr = new int[size];
			for(int i=0; i < size;i++) {
				arr[i] = s.nextInt();		
			}
			
			System.out.println("The original array is ");
			for(int x : arr) {
				System.out.print(x + " ");
			}
			
			reverse(arr);
			System.out.println();
			
			System.out.println("The reverse array is ");
			for(int x : arr) {
				System.out.print(x + " ");
			}
			
			int[] totalSum = sumEvenOdd(arr);
			System.out.println();
			System.out.println("sumEven "+totalSum[0] + " " +"sumOdd "+ totalSum[1]);
			
			System.out.println("The average array is ");
			System.out.println(average(arr));
			
			
			
		}
		
		
		
		
	}
	// *************************************methods
	public static void reverse (int[] arr) {
		int temp;
		int n = arr.length;
		for(int i=0;i< (n/2) ;i++) {
			temp = arr[i];
			arr[i] = arr[n-(i+1)];
			arr[n-(i+1)] = temp;
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

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		System.out.println("Enter number of rows and colums");
		Scanner scan = new Scanner(System.in);
		int n = scan.nextInt();
		int m = scan.nextInt();
		
		if(n != m) {
			int[][] matrix = new int [n][m];
			System.out.println("Enter elements");
			for(int i=0;i<n;i++) {
				for(int j=0;j<m;j++) {
					matrix[i][j] = scan.nextInt();
				}
			}
			
			for(int i=0;i<n;i++) {
				for(int j=0;j<m;j++) {
					System.out.print(matrix[i][j] + " ");
				}
				System.out.println();
			}
						
			
				System.out.println();
				transpose(matrix);
			
			
		}
	}
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

	public static void main(String[] args) {
		
		Scanner sc = new Scanner(System.in);
		System.out.println("Enter Size of the Array");
		int size = sc.nextInt();
		int[] arr = new int [size];
		
		System.out.println("Enter Array elements");
		for(int i=0;i<size;i++) {
			arr[i] = sc.nextInt();
		}
		System.out.println("Original array is ");
		for(int i=0;i<size;i++) {
			System.out.print(arr[i] + " ");
		}
		System.out.println();
		
		System.out.println("Enter Your Moving Element");
		int value = sc.nextInt();
		moveValuee(arr,value);
	}
	
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

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		int n;
		Scanner scan = new Scanner(System.in);
		n = scan.nextInt();
		System.out.println(fibonacci_nth(n));
		System.out.println(fibo(n));
	}
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



