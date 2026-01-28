# DSA-1
Module 1 : Intermediate DSA Concept and Question
  Array: Continous memory allocation with same data type.
    int[] arr = new int[size];
    int arr[] = new int[size];
    int[] arr = {1,2,3,4};
    
*************************************************************
Topic 1 : Reverse an array:
  Given >>>  int[] arr = {1,2,3,4,5};
  Return >>> arr = {5,4,3,2,1};
<img width="1029" height="280" alt="image" src="https://github.com/user-attachments/assets/24809f8b-38b0-430b-89c2-d63d2de2da3a" />

  To create a reuseable function:

  public void reverseArr(int[] arr)
  {
     int L = 0, R = arr.length-1;
      while(l<r)
        {
            int temp = arr[L];
                arr[l]=arr[R];
                arr[R] = temp;
            R--;
            L++;
        }
  }

Time Complexity : O(N)

  * Call above function to reverse an array.

*****************************************************************************************************

#Reverse Particular part of an array: From Element 4 to 6 reverse in array.
Given >>> int[] arr = { 1, 2, 3, 4, 5, 6};
          int startElement = 4, endElement = 6;
Return >>> int arr = { 1, 2, 3, 6, 5, 4};

Code : 

public void reverseParticularArr( int[] arr, int startElement, int endElement)
{
      int L = startElement, R = endElement;
    
      while(L<R)
      {
        int temp = arr[L];
        arr[L] = arr[R];
        arr[R] = temp;

        L++;
        R--;
      }
  }
  
***************************************************************************************************

Topic 2 : Rotate an array K time

Given  :  int[] arr = { 1,2,3,4,5}; int k = 2 ;
Return :  int[] arr = { 4,5,1,2,3};


@Approach 1 :

Now according to Brute force approach we need to rotate K time so T.C = O(K*N).
    Rotate array K times.

    for(int i=1;i<=k;i++)
    {  
      int temp = arr[arr.length-1];
      for(int j=1;j<arr.length-1;j++)
        {
            arr[j] = arr[j-1];
        }
        arr[0]=temp;
    }

  * if rotating K time using above logic , TC = O(K*N), SC = O(1)

======================================================================================

@Approach 2 : 

Given >>>    { 1, 2, 3, 4, 5, 6, 7, 8} , Rotate 4 Times
Return >>>   { 5, 6, ,7 ,8, 1, 2, 3, 4}

<img width="1200" height="409" alt="image" src="https://github.com/user-attachments/assets/d41e0db2-32c0-41df-880f-8ba3e307f07a" />


Observation: Last 4 Element comes and seat in first 4 place and remaining element shifted by 4 Element.
            So if we are shifting K element then last K element move to first place and then put all other element.

            To store these element in required order we need an array with N size . 

            int ans[] = new int[arr.length];   // required array

            for(int i=0;i<K;i++)
            {
              ans[i]=arr[arr.length-K];
            }

            int actualIndex = 0 ;

            for( int i= k+1;i<arr.length;i++)
            {
              ans[i] = arr[actualIndex];
              actualIndex++;
            }


    * Now , in ans array we will ans K rotate result
    * TC = O(N) , SC = O(N)

======================================================================================

@Approach 3 : Here we will reduce SC too.

<img width="1147" height="92" alt="image" src="https://github.com/user-attachments/assets/8c941fda-e24a-4e26-b6bf-46ce7182baed" />
<img width="1234" height="101" alt="image" src="https://github.com/user-attachments/assets/d891240e-5c23-452b-935d-725740c0f40b" />
<img width="1150" height="93" alt="image" src="https://github.com/user-attachments/assets/446727a7-d1dc-43e4-9db7-b99cd53910a4" />

Here, We are reversing the complete array so the last K element will come in front, then in reverse array we are reversing first K element and then last K-N Element.

Given >>>>    arr = { 1,2,3,4,5,6,7,8,9 }; K = 5
Return >>>>   ans = { 5,6,7,8,9,1,2,3,4 }

Intermidate Steps 1 : Reverse the original array
                    arr = { 9,8,7,6,5,4,3,2,1 }
Intermidate Steps 2 : Reverse first K element and last N-K element
                    arr = { 5,6,7,8,9, 1,2,3,4 }


Step 1 :
public void reverseArray(int[] arr)
                      { 
                          int L = 0, int R = 0;
                          while(L<R)
                              {
                                 int temp = arr[L];
                                     arr[L] = arr[R];
                                     arr[R] = temp;

                                    L++;
                                    R--;
                                }
                        }

Step 2 :

public void reverseParticularArray( int[] arr, int startElement, int EndElement)
        {
              int L = startElement, R = endElement;
              while(L<R)
                  {
                      int temp = arr[L];
                          arr[L] = arr[R];
                          arr[R] = temp;
                          L++;
                          R--;
                    }
        }


  Above function we will call 2 times.

  reversparticularArray( arr, 0 , K);
  reverseparticularArray( arr, k+1, N-1);


  * Here our TC = O(N), SC = O(1)

  * Note :
      If,  K>N, k=K%N
           K=N ,  arr will be the same.
    

****************************************************************************************************

Question: 
1. Reverse an array.
2. Reverse array from S element to E element.
3. Rotate array K time.






        
              
          
          
              
  

