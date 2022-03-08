//Inserting-node-at-the-front
//inserting new node at the front of linked list, c++
//creating linked list.
#include<iostream>
using namespace std;

class Node{
	public:
	//creating linked list structure.
		int value;
		Node*Next;
};
  void printlist(Node*n){
  	while(n!=NULL){
  	cout<<n->value<<endl;
  	n=n->Next;
	  }
  	 }
  void insert_At_The_Front(Node**Head,int newValue){
  	//1. prepare new node 
  	Node*newNode=new Node();//newNode is the name of our new node
  	newNode->value=newValue;//newValue i the name of data
  	
	//2.put newNode at the front of our previous head, or give value to the pointer
  	newNode->Next=*Head;
  	//3. now newNode is our HEAD so point it to head
  	*Head=newNode;
  	
  }


int main(){
	//creating 3 new nodes.
	Node*Head=new Node();
	Node*second=new Node();
	Node*third=new Node();
   //giving values to Head, second and third nodes.
   Head->value=1;
   second->value=2;
   third->value=3;
   //giving pointers to each nodes.
   Head->Next=second;
   second->Next=third;
   third->Next=NULL;
   
   insert_At_The_Front(&Head,-1);
   
   //Printing values of each nodes of linked list.
   printlist(Head);
	return 0;
}
