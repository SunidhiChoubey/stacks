# Experiment-18
# stacks
## Aim- To study and implemnet stack operations 
## Theory-
A stack is a fundamental and widely used sequential data structure that adheres to the Last In, First Out (LIFO) principle. This concept means that the last item to be added to the stack will be the first one to be removed. Imagine a stack of plates: when plates are stacked on top of each other, the last plate added is the first one you would remove. Similarly, in a stack data structure, only the top element (the most recent addition) is accessible at any given time for removal, while elements below it are inaccessible until the top element is removed.

Characteristics of a Stack:
LIFO Behavior: The defining feature of a stack is its LIFO nature, where the most recent element is always the first to be removed.
Sequential Access: Unlike arrays or lists that allow random access, stacks only allow access to the topmost element.
Restricted Operations: Operations on a stack are limited to pushing (adding), popping (removing), and peeking (viewing) elements from the top.
Components and Key Operations of a Stack:
Push Operation:

The push operation is used to insert an element onto the stack. When an item is pushed onto the stack, it is placed on the top of the stack, becoming the new top element.
If the stack has a fixed maximum capacity, pushing an element onto a full stack will result in an overflow error (in some implementations).
Pushing an element involves placing the new element at the top of the stack and adjusting the pointer or reference that tracks the current top of the stack.
## Code-
~~~
#include <iostream>
using namespace std;

class Stack 
{
private:
    int top;       
    int maxSize; 
    int* stackArray; 

public:

    Stack(int size) 
    {
        maxSize = size;              
        stackArray = new int[maxSize]; 
        top = -1;                    
    }

    ~Stack() {
        delete[] stackArray;
    }

   
    bool isEmpty() 
    {
        return top == -1;
    }

    bool isFull() 
    {
        return top == maxSize - 1;
    }

    void push(int value) 
    {
        if (isFull()) 
        {
            cout << "Stack Overflow! Unable to push " << value << endl;
            return; 
        }
        stackArray[++top] = value;
        cout << value << " pushed to stack." << endl;
    }

    int pop() 
    {
        if (isEmpty()) 
        {
            cout << "Stack Underflow! Unable to pop." << endl;
            return -1;
        }
        return stackArray[top--];
    }

    int peek() 
    {
        if (isEmpty()) 
        {
            cout << "Stack is empty. No top element." << endl;
            return -1;
        }
        return stackArray[top];
    }

    void display() 
    {
        if (isEmpty()) 
        {
            cout << "Stack is empty." << endl;
            return;
        }
        cout << "Stack elements: ";
        for (int i = top; i >= 0; i--) 
        {
            cout << stackArray[i] << " ";
        }
        cout << endl;
    }
};

int main() 
{
    int size, choice, value;

    cout << "Enter the size of the stack: ";
    cin >> size; 
    Stack stack(size);

    do 
    {
        cout << "\nMenu:\n";
        cout << "1. Push\n";
        cout << "2. Pop\n";
        cout << "3. Peek\n";
        cout << "4. Display\n";
        cout << "5. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1: 
                cout << "Enter value to push: ";
                cin >> value; 
                stack.push(value);
                break;
            case 2:
                value = stack.pop(); 
                if (value != -1)
                    cout << value << " popped from stack." << endl;
                break;
            case 3:
                value = stack.peek();
                if (value != -1)
                    cout << "Top element is: " << value << endl;
                break;
            case 4:
                stack.display();
                break;
            case 5:
                cout << "Exiting program." << endl;
                break;
            default:
                cout << "Invalid choice! Please try again." << endl;
        }
    } 
    while (choice != 5);
    return 0;
}
~~~
## Output-
![](https://github.com/SunidhiChoubey/stacks/blob/main/Screenshot%202024-10-21%20022726.png)
![](
## Conclusion- 
We learnt about stacks in C++ and We learnt the various operations of stack in C++.
