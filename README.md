#include<iostream>
#include<bits/stdc++.h>
#include<cmath>
using namespace std;
bool checkPrime(int n){
	if(n<2){
		return false;
	}else{
		for(int i=2;i<=sqrt(n);i++){
			if(n%i==0){
				return false;
			}
		}
		return true;
	}
}
int main(){
	int n;
	cout<<"Enter the number: ";
	cin>>n;
	int max=n-1;
	int min=2;
	while(true){
		if(checkPrime(max) && checkPrime(min)){
			if((max+min)<=n){
				break;
			}
		}
		if((max + min) >=n){
            max--; 
        } else {
            min++; 
        }
	}
	cout<<"("<<max<<","<<min<<")"<<endl;
	return 0;
}
