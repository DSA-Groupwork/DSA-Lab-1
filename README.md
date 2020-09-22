# DSA-Lab-1
# Lab About Time space errors



 # Integer overflow



#include<iostream>
using namespace std;

int main(){

 	unsigned short uShortValue =65535;
 	cout<<"increment unsigned short"<<uShortValue<<"gives:";
 	cout<<++uShortValue<<endl;
 	
 	short signedShort =32767;
 	cout<<"incrementing signed short"<<signedShort<<"gives:";
 	cout<<++signedShort<<endl;
 	
 	return 0;
}

![Screenshot (79)](https://user-images.githubusercontent.com/64952843/93900587-3dfb6600-fcfe-11ea-89a4-10b7497925c3.png)

error was when we exceed the limit imposed by the type chosen in an arithmetic operation, when we increment the value in unsigned short the values overflow to 0. This can be avoided when selecting correct data types .

 # sign error
 
#include<iostream>
using namespace std;

int main(){

	short signed i=-32767;
       short unsigned u=i;
	cout<<"The result of u:"<<u<<endl;
}
![Screenshot (82)](https://user-images.githubusercontent.com/64952843/93899197-bcef9f00-fcfc-11ea-8ef7-826dd8a3c688.png)

The error arise when converting from signed to unsigned variables .in the example above if you have a negative signed value(short i = -32767) and you were to assign that value to unsigned  variable (unsigned short u=i),the internal representation of the number is unchanged ,but the  resulting value is being unsigned ,leading to an undesired result (u=32769)

 # Transaction

#include<iostream>
using namespace std;

int main(){

	long l = 32800;
        short s = (short)l;
	cout<<"The result of u:"<<s<<endl;
}
![Screenshot (83)](https://user-images.githubusercontent.com/64952843/93899777-56b74c00-fcfd-11ea-9f82-0411757726cb.png)

The error was when we assigned  long to a short(short s =(short)l;) will cause truncation. 



 # QUESTION 2
#include<iostream>
using namespace std;

void printarray(int arg[],int length){

	for(int n=0;n<length;n++)
	cout<<arg[n]<<"";cout<<"\n";
}

int main(){

	int firstarray[]={5,10,15};
	int secondary[]={2,4,6,8,10};
	printarray(firstarray,2);
	printarray(secondary,5);
	return 0;
}

![Screenshot (84)](https://user-images.githubusercontent.com/64952843/93898750-39ce4900-fcfc-11ea-931a-c7dc393e9752.png)

Array parameters being adjusted to pointer parameters and array arguments being converted to pointer arguments .the first in an adjustment to the actual type of the parameter, whereas the other is a standard conversion which introduces a temporary pointer to the first element. Firstarray and secondarray are converted to pointer to int, when passed to printarray(). So in printarray(firstarray,3); the value firstarray of type array of 3 int is converted to a pointer value(temporary) of type pointer to int pointing to the first element.so int arg[] is adjusted to be int* arg.
	

