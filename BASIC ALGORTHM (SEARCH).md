# Linear Search Algorithm 

## Unsorted

![Linear Search - GeeksforGeeks](https://media.geeksforgeeks.org/wp-content/cdn-uploads/Linear-Search.png)

```java
int a[]={1,5,4,10,12}
for(int i=0;i<a.length;i++){
    if(a[i]==4){
        sout("num is found");
        break;
    }
}
```

# Binary Search Algorithm

## Sorted

![Binary Search - GeeksforGeeks](https://www.geeksforgeeks.org/wp-content/uploads/Binary-Search.png)

low = 0

high = 9

mid = low+(high-low)/2  = 0+(9-0)/2 =4

if the number in right low == mid+1

if the number in light low == mid-1

----------------------------------------------------------------------

low = 4+1 =5

high =9

mid =5+(9-5)/2 =5+2=7

---------------------------------------------

low = 5

high =7-1=6

mid =5+(6-5)=6

high==mid that mean we found number

```java
// Java implementation of recursive Binary Search
class BinarySearch {
	// Returns index of x if it is present in arr[l..
	// r], else return -1
	int binarySearch(int arr[], int l, int r, int x)
	{
		if (r >= l) {
			int mid = l + (r - l) / 2;

			// If the element is present at the
			// middle itself
			if (arr[mid] == x)
				return mid;

			// If element is smaller than mid, then
			// it can only be present in left subarray
			if (arr[mid] > x)
				return binarySearch(arr, l, mid - 1, x);

			// Else the element can only be present
			// in right subarray
			return binarySearch(arr, mid + 1, r, x);
		}

		// We reach here when element is not present
		// in array
		return -1;
	}

	// Driver method to test above
	public static void main(String args[])
	{
		BinarySearch ob = new BinarySearch();
		int arr[] = { 2, 3, 4, 10, 40 };
		int n = arr.length;
		int x = 10;
		int result = ob.binarySearch(arr, 0, n - 1, x);
		if (result == -1)
			System.out.println("Element not present");
		else
			System.out.println("Element found at index " + result);
	}
}
/* This code is contributed by Rajat Mishra */

```

