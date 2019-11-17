# QUICK
* 퀵쇼트

#include <stdio.h> 

#include <stdlib.h> 

int compare(const void* a, const void* b) { 

	return (*(int*)a - *(int*)b);

}int main() {       

int v[] = {3,1,2,5,4};

int n; qsort(v, 5, sizeof(int), compare);

for (n = 0; n < 5; n++)  printf("%d ", v[n]);

return 0;}

* 결과
 
 ![결과](https://user-images.githubusercontent.com/50895124/69003868-9f1f1400-094c-11ea-9a0d-089435a0eb84.PNG)


const : 변수를 상수로 바꾸지마라  



#include<stdio.h>

#define LEN 8

void qs(int v[], int left, int right) {

int pivot, pi, l, r, dir;
  
if (left < right) {
  
dir = 0;
    
l = left; r = right; pi = left;
    
pivot = v[pi];
  
  while (l < r) {
    
if (dir == 0) {
      
if (pivot < v[r]) r--;
       
  else {
        
v[pi] = v[r];
          
pi = r;
          
if (l != r) l++;
          
dir = 1;
          
}
    }
      
if (dir == 1) {
     
if (pivot > v[l]) l++;
        
else {
        
v[pi] = v[l];
          
pi = l;
          
if (l != r) r--;
          
dir = 0;
}
        
               
}
   	}
    
v[r] = pivot;
    
qs(v, left, r - 1);
    
qs(v, r + 1, right);
    
}
return;
  
}

void main() {

int i;
  
int v[LEN] = { 8,17,6,5,-44,3,2,1 };
  
for (i = 0; i < LEN; i++) printf(" %d", v[i]); printf("\n");
  
qs(v, 0, LEN - 1);
  
for (i = 0; i < LEN; i++) printf(" %d", v[i]); printf("\n");

* 결과

![구현결과](https://user-images.githubusercontent.com/50895124/69003864-8e6e9e00-094c-11ea-8526-3eb0cd75717b.PNG)
