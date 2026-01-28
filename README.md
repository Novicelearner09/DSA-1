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

  To create a reuseable function:

  public void reverseArr(int[] arr)
  {
  int l = 0, r = arr.length-1;
  while(l<r)
  {
  int temp = arr[l];
      arr[l]=arr[r];
      arr[r] = temp;
  }

  * Call above function to reverse an array.
*********************************************************

Topic 2 : Rotate an array K time

Given  :  int[] arr = { 1,2,3,4,5}; int k = 2 ;
Return :  int[] arr = { 4,5,1,2,3};

Now according to Brute force approach we need to rotate K time so T.C = O(k*N).
    Rotate array K times.

    for(int i=1;i<=k;i++)
    {  
      for(int j=0;j<arr.length-1;j++)
        {
          int temp = arr[0];
              
  

