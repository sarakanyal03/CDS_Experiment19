# EXPERIMENT 19
### AIM
To study and implement queue implementation using array. <BR>
menu options -  <BR>
1) insert <BR>
2) delete  <BR>
3) display  <BR>
4) exit <BR>
### THEORY
*Queue Implementation using Array:* <BR>
<BR>
A queue is a linear data structure that follows the First In First Out (FIFO) principle. The element added first is the first one to be removed. Queue operations primarily include: <BR>
* Enqueue (Insert): Add an element to the rear (end) of the queue. <BR>
* Dequeue (Delete): Remove an element from the front of the queue. <BR>
* Display: Display all the elements in the queue. <BR>
* Exit: Terminate the program. <BR>
 <BR>
In a static array implementation of a queue, we use a fixed-size array and two variables, front and rear, to keep track of the first and last elements of the queue, respectively.  <BR>

* Enqueue Operation (Insertion): <BR>
  * Before inserting an element, check if the queue is full (i.e., rear == MAX_SIZE - 1). <BR>
  * If the queue is not full, increment rear and insert the new element at that position. <BR>

* Dequeue Operation (Deletion): <BR>
  * Before deleting an element, check if the queue is empty (i.e., front == rear). <BR>
  * If the queue is not empty, increment front to remove the element at the front of the queue. <BR>

* Display Operation: <BR>
  * Traverse the array from front + 1 to rear to display the queue elements. <BR>
  
### CODE & OUTPUT
1. CODE A: <BR>
```
//SARA KANYAL
//23070123115
//eEXPERIMENT 19-A
#include <iostream>
using namespace std;
int queue[100], n = 100, front = - 1, rear = - 1;
void Insert() {
   int val;
   if (rear == n - 1)
   cout<<"Queue Overflow"<<endl;
   else {
      if (front == - 1)
      front = 0;
      cout<<"Insert the element in queue : "<<endl;
      cin>>val;
      rear++;
      queue[rear] = val;
   }
}
void Delete() {
   if (front == - 1 || front > rear) {
      cout<<"Queue Underflow ";
      return ;
   } else {
      cout<<"Element deleted from queue is : "<< queue[front] <<endl;
      front++;;
   }
}
void Display() {
   if (front == - 1)
   cout<<"Queue is empty"<<endl;
   else {
      cout<<"Queue elements are : ";
      for (int i = front; i <= rear; i++)
      cout<<queue[i]<<" ";
         cout<<endl;
   }
}
int main() {
   int ch;
   cout<<"1) Insert element to queue"<<endl;
   cout<<"2) Delete element from queue"<<endl;
   cout<<"3) Display all the elements of queue"<<endl;
   cout<<"4) Exit"<<endl;
   do {
      cout<<"Enter your choice : "<<endl;
      cin>>ch;
      switch (ch) {
         case 1: Insert();
         break;
         case 2: Delete();
         break;
         case 3: Display();
         break;
         case 4: cout<<"Exit"<<endl;
         break;
         default: cout<<"Invalid choice"<<endl;
      }
   } while(ch!=4);
   return 0;
}
```
* OUTPUT A: <BR>
![EXP19A](https://github.com/sarakanyal03/CDS_Experiment19/blob/main/19A.png)
2.  CODE B: <BR>
```
//SARA KANYAL
//23070123115
//EXPERIMENT 19-B
#include <iostream>
using namespace std;
#define size 5
#define ERROR -9999

class Queue {
    int rear, front, arr[size];
public:
    Queue() {
        rear = -1;
        front = -1;
    }
    void enqueue(int);
    int dequeue();
    void disp();
};
void Queue::enqueue(int num) {
    if (rear == size - 1) {
        cout << "Queue is full" << endl;
    } else {
        if (front == -1) {
            front = 0;
        }
        arr[++rear] = num;
    }
}
int Queue::dequeue() {
    if (front == -1 || front > rear) {
        cout << "Queue is empty" << endl;
        return ERROR;
    } else {
        return arr[front++];
    }
}
void Queue::disp() {
    if (front == -1 || front > rear) {
        cout << "Queue is empty" << endl;
    } else {
        cout << "Queue elements: ";
        for (int i = front; i <= rear; i++) {
            cout << arr[i] << " ";
        }
        cout << endl;
    }
}

int main() {
    Queue q1;
    q1.enqueue(4);
    q1.enqueue(8);
    q1.enqueue(3);
    q1.disp();
   
    int val = q1.dequeue();
    cout << "Deleted element: " << val << endl;
   
    q1.disp();
   
    return 0;
}
```
* OUTPUT B: <BR>
![EXP19B](https://github.com/sarakanyal03/CDS_Experiment19/blob/main/19B.png)
### CONCLUSION
This C++ example shows the fundamental operations of a queue using an array. The array's fixed size indicates that the queue has a limited capacity, which can result in overflow problems if the number of elements exceeds the array size.
