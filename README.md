# dsa-codes
#include<iostream>
using namespace std;

struct node{
    int value;
    node* next;
};

node* head = NULL;

void createL(){
    int choice;
    do {
        node* newnode = new node;
        cout << "enter the value" << endl;
        cin >> newnode->value;
        newnode->next = NULL;

        if(head == NULL){
            head = newnode;
        }
        else {
            node* temp = head;
            while(temp->next != NULL){
                temp = temp->next;
            }
            temp->next = newnode;
        }
        cout << "0 (no) or 1 (yes)" << endl;
        cin >> choice;
    } while(choice != 0);
}

void display(){
    node* temp = head;
    if(head == NULL){
        cout << "list is empty" << endl;
    }
    while(temp != NULL){
        cout << temp->value << " ";
        temp = temp->next;
    }
}

int main(){
    createL();
    display();
    return 0;
}
