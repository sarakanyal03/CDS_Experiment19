# CDS_Experiment18
# AIM
# THEORY
*Queue Implementation using Array:* <BR>
<BR>
A queue is a linear data structure that follows the First In First Out (FIFO) principle. The element added first is the first one to be removed. Queue operations primarily include: <BR>
Enqueue (Insert): Add an element to the rear (end) of the queue. <BR>
Dequeue (Delete): Remove an element from the front of the queue. <BR>
Display: Display all the elements in the queue. <BR>
Exit: Terminate the program. <BR>
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
  
# CODE & OUTPUT
# CONCLUSION
