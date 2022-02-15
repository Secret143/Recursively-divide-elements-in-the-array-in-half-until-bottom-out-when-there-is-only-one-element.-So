

#include<stdio.h>

int n;

void merge(int a[],int low, int mid, int up){

    

    int b[n];

    int i=low;

    int j=mid+1;

    int k=low;

    while(i<=mid && j<=up){

    

        if(a[i]<=a[j]){

            b[k]=a[i];

            i++;

        }

        else{

            b[k]=a[j];

            

            j++;

         }

         k++;

     }

    

        while(j<=up){

            

            b[k]=a[j];

            k++;

            j++;

        }

    

    

        while(i<=mid){

            b[k]=a[i];

            k++;

            i++;

        }

    

       for(int x=low; x<=up;x++){

        a[x]=b[x];

        

      }

}

void mergeSort(int a[],int low,int up){

    

    if(low<up){

    int mid=(low+up)/2;

    mergeSort(a,low,mid);

    mergeSort(a,mid+1,up);

    merge(a,low,mid,up);

    }

}

void main(){

    int i;

    scanf("%d",&n);

    int a[n];

    for(i=0;i<n;i++){

        scanf("%d",&a[i]);

    }

    mergeSort(a,0,n-1);

    for(int i=0;i<n;i++){

        printf("%d ",a[i]);

    }

    

}
