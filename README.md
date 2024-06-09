# Infinite-search
Search in infinitely long sorted array with binary search to optimize the time complexity 
//Search in infinite sorted array
#include<iostream>
using namespace std;

int binSearch(int arr[],int x,int low,int high){
	while(low<=high){
		int mid=(low+high)/2;
		if(arr[mid]=x){
			return mid;
		}
		else if(arr[mid]>x){
			high=mid-1;
		}
		else{
			low=mid+1;
		}
	}
	return -1;
}

int search(int arr[],int x){
	if(arr[0]==x){
		return 0;
	}
	int i=1;
	while(arr[i]<x){
		i=i*2;
	}
	if(arr[i]==x){
		return i;
	}
	
	return binSearch(arr,x,i/2 +1,i-1);
}

