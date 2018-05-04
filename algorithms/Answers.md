Exercise I. Give an analysis of the running time with respect to the input size n of each of the following program fragments: 

a) a = 0;
   while (a < n * n * n)
	 a = a + n * n;

	 running time = O(n);

b) // input array is of length n
   i = array.length - 1;
	 while (array[i] > x && i >= 0)
	   i = i/2;

		running time = O(log n)

c) sum = 0;
   for (i = 0; i < Math.sqrt(n) / 2; i++)
			for (j = i; j < 8 + i; j++)
				 for (k = j; k < 8 + j; k++)
					 sum++;

	 running time = O(sqrt(n))

d) sum = 0;
	 for (i = 1; i < n; i *= 2)
		 for (j = 0; j < n; j++)
			 sum++;
	
	running time = O(n log n)

e) sum = 0;
		 for (i = 0; i < n; i++) 
			 for j = i + 1; j < n; j++)
			   for (k = j + 1; k < n; k++)
					 for (l = k + 1; l < 10 + k; l++)
						 sum++;

	 running time = O(n^3)

f) bunnyEars = function (bunnies) {
			if (bunnies === 0) return 0;
			return 2 + bunnyEars(bunnies-1);
		}

		running time = O(n)

g) search = function (array, arraySize, target) {
		 if (arraySize > 0) {
		    if (array[arraySize-1] === target) return true;
				else return search(array, arraySize-1, target);
			}
				return false;
			}
   
    running time = O(n)

Exercise II

a) Given an array a of n numbers, design a linear running time algorithm to
   find the maximum value of a[j] - a[i], where j > i.

	 function maxValueDifference(array) {
		   let minimum = array[0];
			 let maximum = array[0];

			 for (let i = 0; i < array.length; i++) {
					 const value = array[i];

					 if (value < min) min = value;
					 if (value > max) max = value;
				}
				  return max - min;
			}

b) Suppose that you have an n-story building and plenty of eggs. Suppose also that
	 an egg is broken if it is thrown off floor f or higher, and unbroken otherwise. 
	 Devise a strategy to determine the value of f such that the number of dropped 
	 eggs is minimized.

  A strategy for breaking less eggs could possibly be to use a binary search tree. Pick
	a floor f and if the egg breaks, move down a floor. Otherwise, move up. Stop if the egg
	doesn't break at a particular floor, but does break at the the floor above that.

	Exercise III. Below is the pseduo-code for the Quicksort algorithm:

	function quicksort(array) 
	   if length(array) <= 1
		   return array 
		 select and remove a pivot element pivot from array
		 create empty lists less and greater
		 for each x in array
		    if x <= pivot then append x to less
				else append x to greater 
			return concatenate(quicksort(less), list(pivot), quicksort(greater))
	  
	 a) Suppose we implement quicksort so that the pivot is always chosen to be the first 
	    element of the array. What is the running time of this algorithm on an input array 
			that is already sorted? Why? 

			If quicksort is implemented with the pivot being chosen as the first element of the array, 
			the worst case of Quicksort occurs because the Array is either already sorted in the same order,
			the Array is already sorted in reverse order or all elements are the same. As the algorithm is iterated,
			the left array remains empty and the right is n - 1, n - 2 etc and for this reason, the complexity is O(n^2).

	 b) Suppose we implement quicksort so that the pivot is always magically chosen to be the median element of the
	    array. What is the running time of this algorithm? Why?
     
      If quicksort is implemented with the pivot being chosen as the median element of the array, quicksort is a divide and 
			conquer algorithm that divides a large array into two smaller sub-arrays: the low elements and the high elements which are recursively sorted. 
			The running time for this algorithm is (log n) for both of the arrays and at each point has linear complexity, making it O(n log n).

