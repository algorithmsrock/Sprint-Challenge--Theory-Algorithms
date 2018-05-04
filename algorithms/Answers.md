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
