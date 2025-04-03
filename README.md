# linked
#include<bits/stdc++.h>
using namespace std;
struct node{
    int data;
    node* next;

};
node* linked(int n){
    node* head=new node;
    cout<<"enter the data un the head"<<endl;
    cin>>head->data;
    head->next=nullptr;
    node* temp=head;
    for(int i=2;i<=n;i++){
        node* newnode=new node();
    cin>>newnode->data;
     newnode->next=nullptr;
     temp->next=newnode;
     temp=newnode;
    }
    temp->next=head;
    return head;

}
void display(node* head){
 
    node* temp =head;
    do{
        cout<<temp->data <<"and"<<temp->next<<endl;
        temp=temp->next;
    }
    while(temp!=head);
    
}
node* deleteatbeg(node* head) {
    cout<<"after the deletion"<<endl;
    if (head == NULL) return NULL;  // Empty list case

    node* temp = head;
    
    // If only one node is present
if (head->next == head) {
        delete head;
        return NULL;
    }

    node* last = head;
    
    // Find the last node
    while (last->next != head) {
        last = last->next
    }

    // Update last node's next pointer to the second node
    head = head->next;
    last->next = head;

    delete temp; // Free memory of old head

    return head;
}
int main(){
    int n;
    cout<<"enter the mo of term in the linked list"<<endl;
    cin>>n;
    node* head=linked(n);
    display(head);
    node* hea=deleteatbeg(head);
    display(hea);
}

