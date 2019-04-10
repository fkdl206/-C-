#define _CRT_SECURE_NO_WARNINGS 
#include<stdio.h> 
#include<stdlib.h> 
#include<time.h> 
#include<ctype.h>
void swap(int *x, int *y, int *t)  { 
 *t = *x; 
 *x = *y; 
 *y = *t;
} 
int partition(int list[], int left, int right)  { 
    int pivot,temp; 
    int low,high; 
    int i; 
    low=left; 
    high=right+1; 
    pivot=list[left]; 
    do { 
        do { 
            low++; 
        } while(low<=right &&list[low]<pivot);  
        do {  
            high--; 
        } while(high>=left && list[high]>pivot); 
        if(low<high) {
            swap(&list[low],&list[high], &temp);
        }
    } while(low<high); 
    swap(&list[left], &list[high], &temp); 
    printf("----파티션 후 리스트----\n"); 
    for(i=0; i<right+1; i++) {

        printf("%4d ", list[i]); 
    }
    printf("\nhigh값 %d \n",high); 
    return high; 
}
int Selection(int list[], int left, int right, int k) { 
    int temp,pivot,pivot_index; 
    int s,q,i; 
    pivot_index = rand()%(right-left+1)+left; 
    pivot = list[pivot_index]; 
    swap(&list[pivot_index], &list[left], &temp); 
    q = partition(list,left,right); 
    s=(q-1)-left+1; 
    if (k<=s) {
        Selection(list,left,q-1,k); 
    } else if(k==s+1) {
        return list[q];
    } else {
        Selection(list,q+1,right,k-s-1); 
    }
}

int main(void) { 
    int n=100; 
    int i,k,right,left; 

    int result; 
    char ch; 
    srand((unsigned)time(NULL)); 
    int list[100]; 
    for(i=0;i<100;i++) {
        list[i] = rand()%9000+1000; 

    }
    do {
        for (i = 0; i < 100; i++) {
            printf("%d ", list[i]);
        }
        printf("\n"); 
        left=0; 
        right=n-1; 
        while(1) { 
            printf("몇 번째로 작은수를 찾을거야? "); 
            scanf("%d",&k); 
            if(1<=k && k<=n) {
                break;
            } else {
                printf("k 다시 입력 \n"); 
            }
        }
        printf("%d등 = %d\n",k,Selection(list,left,right,k)); 
        printf("한 번 더 하시겠습니까???(Y/N)"); 
        scanf(" %c", &ch);
    } while( toupper(ch) == 'Y');
} 
