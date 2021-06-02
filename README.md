#// PALAKBANSAL
//merge sort code
package mergesort;

public class MyMergeSort {
    public  void mergesort(int arr[],int p , int q, int r ){
        int n1=q-p+1;
        int n2=r-q;
        int L[] =new int[n1];
        int M[] =new int[n2];
        for (int i=0 ;i<n1;i++)
            L[i]=arr[p+i];
        for(int j =0;j<n2;j++)
            M[j]=arr[q+1+j];
        int i,j,k;
        i=0;
        j=0;
        k=p;
        while (i<n1 && j<n2) {
            if(L[i]<=M[j]){
                arr[k]=L[i];
                i++;
            }
            else{
                arr[k]=M[j];
                j++;
            }
            k++;
        }
       while(i<n1){
           arr[k]=L[i];
           i++;
           k++;
       }
       while(j<n2){
           arr[k]=M[j];
           j++;
           k++;

       }
    }
    public void mergesort(int arr[],int l,int r){
        if(l<r){
            int m=(l+r)/2;
            mergesort(arr,l,m);
            mergesort(arr,m+1,r);
            mergesort(arr,l,m,r);
        }
    }
    public static void printArray(int arr[]){
        int n = arr.length;
        for(int i=0;i<n;++i)
            System.out.print(arr[i] + " ");
        System.out.println();

    }
    public static void main (String args[]){
        int arr[] ={6,5,12,10,9,1};
        MyMergeSort ob = new MyMergeSort();
        ob.mergesort(arr,0,arr.length-1);
        System.out.println("Sorted array : ");
        printArray(arr);

    }
    }

