Search an element in a matrix in C
Here, in this page we will discuss the program to search an element in a matrix in C programming language. We are given with an n x n matrix, and the value of the element that need to be searched in the given matrix.We have to find the position of searched element in the matrix if it is present in it. Otherwise, we need to print “Not Found”. In the given matrix, every row and column is sorted in increasing order.

search an element in matrix in C
While loop in C
Method 1 :
Create a variable search that store the value of the element that need to be searched and also declare a int type variable say flag initialized with 0, that becomes true if element is present in the given matrix.
Now, run a nested for loop that will iterate over the matrix and check if current value is equal to the searched value.
If it is then print its position and makes the value of flag = 1, then break the loop.
Now, if flag becomes 1 then also break the outer loop.
After coming out from the nested loop, if flag==0 then print “Not Found”
Time and Space Complexities :
Time-Complexity :O(n^2)
Space-Complexity : O(1)
Search an element in a matriix
Method 1 : Code in C
Run
#include <stdio.h>
int main(){

    int a[4][4] = {{0,1,12,3}, {4,5,6,7}, {8,9,10,11}};;
   
    int search = 6;
    int flag=0;

    for(int i=0; i<4; i++){

        for(int j=0; j<4; j++){
            if(a[i][j]==search){
                printf("Element is found at (%d, %d) position",i,j);
                flag=1;
                break;
            }
        }

        if(flag==1)
            break;
    }

    if(flag==0)
        printf("Not found");
}
Output :
Element found at (1, 2) position
Method 2 :
Take two variables say i and j, set i at 0 and j at n-1.
Run a loop  that will terminate when i>n
Now, If the current element is greater than x then decrease the count of j. Exclude the current column.
And If the current element is less than x then increase the count of i. Exclude the current row.
If the element is equal, then print the position, set flag = 1 and break the loop.
After coming out from the loop, if flag==0 then print “Not Found”
Time and Space Complexities :
Time-Complexity :O(n)
Space-Complexity : O(1)
Method 2 : Code in C
Run
#include <stdio.h>

int main(){

    int a[4][4] = {{0,1,12,3}, {4,5,6,7}, {8,9,10,11}};;
   
    int x = 6;
    int flag=0;

    int i=0, j=3;
  
    while (i < 3 && j >= 0)
    {
        if (a[i][j] == x)
        {
                printf("Element is found at (%d, %d) position",i,j);
                flag=1;
                break;
        }
        if (a[i][j] > x)
            j--;
        else
            i++;
    }

  if(flag==0)
    printf("Not found");
}
Output :
Element found at (1, 2) position
