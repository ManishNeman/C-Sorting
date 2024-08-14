# C-Sorting
# By using Bubble sort and Insertion sort for sorting of  STUDENT , SGPA , and ROLL NUMBER

#include<iostream> 
using namespace std;
void bubblesort(int arr[],int n){
    bool swap;
    for(int i=0;i<=n-1;++i){
        swap=false;
        for(int j=0;j<n-i-1;++j){
            if(arr[j]>arr[j+1]){
                int res=arr[j];
                arr[j]=arr[j+1];
                arr[j+1]=res;
                swap=true;
            }
        }
        if(!swap) break;
    }
}


void insertion (int arr[], int n ){
    for(int step=1;step<n;step++){
        int key=arr[step];
        int j= step -1;
        
        
        while(key<arr[j] && j>=0){
            arr[j+1]=arr[j];
            --j;
        }
        arr[j+1]=key;
    }
}

void search(float arr[],int n){
   for(int i=0;i<=n;i++){
    float c=9.05;
   
   
        if(c==arr[i]){
            cout<< "SGPA " <<c<< " "<<"found at index"<< " " << i << endl;
         }
   }
}



int main(){
    
int rollno[]={17,16,11,12,10,1,18,15,14,2,3,4,7,8,9,5,6,19,20,21};
string name[]={"          Ram        ","          Yogesh     ","          Chaitanya  ","          Soham      ","          Pawan      ","          Satyam     ","          Sumit      ","          Ritesh     ","          Abhishek   ","         Sahil      ","         Sujal      ","         Mayur      ","         Pankaj     ","         Krishi     ","         Samir      ","         Tanmay     ","         Arbaj      ","         Ravi       ","         Sarthak    ","         Vedant     "};
float sgpa[]={9.1,9.2,8,7.8,8.7,9.6,9.6,8.6,9.05,9.05,10,8,9,9.05,9.1,8,7,7.5,8.6,9.8};

int n=sizeof(rollno)/sizeof(rollno[0]);
bubblesort(rollno,n);
insertion(rollno,n);

cout<<"Roll No       Name              Sgpa"<<endl;

for(int i=0;i<=19;i++){
cout<<rollno[i]<<"   ";

cout<<name[i]<<"       ";

cout<<sgpa[i]<<"\n";
}

cout<<""<<endl;
search(sgpa,n);

return 0;
}
