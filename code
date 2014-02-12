import java.io.BufferedReader;//import reader
import java.util.Scanner;// import scanner
import java.io.File;
import java.io.FileReader;// import file reader
import java.io.PrintStream;
import java.util.ArrayList;// import array list 

public class sorting_arrays { // create a class
	public static void main(String[] args) throws Exception {
		Scanner input = new Scanner(System.in);// Setup scanner
		File f = new File("RandomNumbers.txt"); // the number file
		FileReader fr = new FileReader(f); // read file
		BufferedReader br = new BufferedReader(fr);

		ArrayList<Integer> array = new ArrayList<Integer>();//declaration 
		String s = br.readLine(); // read file
		while (s != null) {
			array.add(Integer.parseInt(s));
			s = br.readLine();
		}

		int[] iArray = new int[array.size()];// new array
		for (int i = 0; i < array.size(); i++) //for loop for array before sorted
			iArray[i] = array.get(i); // the array
		int userinput = 0;// intalise variable
		// print statements
		System.out.println("Please enter 1 for bubble sort");
		System.out.println("Please enter 2 for selection sort");
		System.out.println("Please enter 3 for insertion sort");
		System.out.println("Please enter  4 for merge sort");
		System.out.println("Please enter 5 quick sort");
		System.out.println("Please enter 0 to exit");

		userinput = input.nextInt();
// user input validation
		while(userinput >= 0)// while loop
		{
			if(userinput == 0)
			{
				System.out.println("Closing program...");// close program if user enters o
				System.exit(1);
			}
			
			while(userinput >= 1 && userinput <= 5)
			{// if user user picks a number
				if (userinput == 1) {
					System.out.println("you have picked bubblesort");
					bubbleSort(iArray);
					
				} else if (userinput == 2) {
					System.out.println("you have picked selectionsort");
					selectionSort(iArray);
		
				} else if (userinput == 3) {
					System.out.println("you have picked mergesort");
					mergesort(iArray);
		
				} else if (userinput == 4) {
					System.out.println("you have picked insertionsort");
					insertionsort(iArray);
		
				} else if (userinput == 5) {
					System.out.println("you have picked quicksort");
					quicksort(iArray);
				}
		
				PrintStream out = new PrintStream(new File("output.txt"));
				// send to text file
				for (int i = 0; i < iArray.length; i++)
				{// print out sorted array
					System.out.print(iArray[i] + " ");
					out.print(iArray[i] + " ");
				}
				
				System.out.print("\n\n");
				// back into the loop
				System.out.println("Please enter 1 for bubble sort");
				System.out.println("Please enter 2 for selection sort");
				System.out.println("Please enter 3 for insertion sort");
				System.out.println("Please enter  4 for merge sort");
				System.out.println("Please enter 5 quick sort");
				System.out.println("Please enter 0 to exit");
	
				userinput = input.nextInt();
			}
		}
	}// end loop

	public static void bubbleSort(int[] array) {

		int outer, inner;
		for (outer = array.length - 1; outer > 0; outer--) { // counting down
			for (inner = 0; inner < outer; inner++) { // bubbling up
				if (array[inner] > array[inner + 1]) { // if out of order...
					int temp = array[inner]; // then swap
					array[inner] = array[inner + 1];
					array[inner + 1] = temp;
				}
			}
		}
	}
	public static int[] selectionSort(int[] array1) {
		int outer, inner, minmum;
		for (outer = 0; outer < array1.length - 1; outer++) { // outer count down and variable to 0
			minmum = outer; //assign outer to min value
			for (inner = outer + 1; inner < array1.length; inner++) { // inner loop
				if (array1[inner] < array1[minmum]) {
					minmum = inner;
				}
			}
			int temp = array1[outer];
			array1[outer] = array1[minmum];
			array1[minmum] = temp;
		}
		return array1;
	}// method close
	
	public static void insertionsort(int array[])
	{
		insertionSort(array);
	}

	private static void insertionSort(int array1[]) {

		int n = array1.length;
		for (int i = 1; i < n; i++) { // Smaller values are moving up
			int j = i;
			int b = array1[i];

			while ((j > 0) && (array1[j - 1] > b)) { // while loop
				array1[j] = array1[j - 1];
				j--;
			}// loop close
			array1[j] = b;
		}// method closed
	}
	
	public static void mergesort(int array[])
	{
		mergesort(array, 0, array.length-1);
	}

	private static void mergesort(int array2[], int low, int high) {
		int Low = low;
		int High = high;

		if (Low >= High) { 
			return;
		}// Get the index of the element which is in the middle
		int middle = (Low + High) / 2;// Divide into two equal half
		mergesort(array2, Low, middle);
		mergesort(array2, middle + 1, High);
		int end_low = middle;
		int start_high = middle + 1;
		while ((Low <= end_low) && (start_high <= High)) {//main loop // merge and sort
			if (array2[Low] < array2[start_high]) {//if the first element low is smaller than the first of high
				Low++; // counter
			} else {
				int Temp = array2[start_high];
				for (int k = start_high - 1; k >= Low; k--) {// copy temp back into main list
					array2[k + 1] = array2[k];
				}
				array2[Low] = Temp;
				Low++;
				end_low++;
				start_high++;
			}
		}// close the method
	}
	
	public static void quicksort(int array[])
	{
		quicksort(array, 0, array.length - 1);
	}
	
	private static void quicksort(int numbers[], int low, int high) {
	    int i = low, j = high;
	    int pivot = numbers[low + (high-low)/2];

	    // Divide into two lists
	    while (i <= j) {
	      // If the current value from the left list is smaller then the pivot
	      // element then get the next element from the left list
	      while (numbers[i] < pivot) {
	        i++;
	      }
	      // If the current value from the right list is larger then the pivot
	      // element then get the next element from the right list
	      while (numbers[j] > pivot) {
	        j--;
	      } // which is smaller then the pivot element then we exchange the values.
	      //  increase i and j
	      if (i <= j) {
	    	  int temp = numbers[i];
	    	  numbers[i] = numbers[j];
	    	  numbers[j] = temp;
	        i++;
	        j--;
	      }
	    }
	    
	    if (low < j)
	      quicksort(numbers, low, j);
	    if (i < high)
	      quicksort(numbers, i, high);
	  }
}
	//close method
