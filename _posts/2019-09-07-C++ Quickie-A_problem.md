---
layout: post
title: Compilation output Mismatch?
---
*The Weired thing was my machine was producing the wrong result no the cloud. Is my machine alright :(*   


Hi, here a quickie to show before you a weird experience that I had today.   
I was implementing a binary-search-tree algorithm today and encountered that in my local machine the code compiled to give me a wrong output.     

Let me show you what code it was.     

Comments in the code show what the problem is.   

```
// Binary Search Tree Implementation

#include <iostream>
#include <tuple>

using namespace std;

struct node
{
    int val;
    node *left = nullptr;
    node *right = nullptr;
};

node* root = new node; 


/* insert function, takes params as (root node, and value ) to be added to the BST */
void insert(node* t, int a)
{
    if(t->val > a)
    {
        if(t -> left == NULL)
        {
            node* leftChild = new node;
            leftChild -> val = a;
            t -> left = leftChild;
        }
        else
        {
            insert(t->left, a);
        }
    }
    else
    {
        if(t->right == NULL)
        {
            node* rightChild = new node;
            rightChild -> val = a;
            t -> right = rightChild;
        }
        else
        {
            insert(t->right, a);;
        }
    }
}

/* If value a is present in tree return pointer to that node and it's parent.
    The pointers are returned as tuple <node,parent> */
tuple<node*, node*> search(node* t, node* parent, int a)
{
    if (t -> val == a)
    {
        //tuple (child, parent);
        return make_tuple(t, nullptr);
    }

    if(t->val > a)
    {
        if(t -> left == nullptr)
            return make_tuple(nullptr, nullptr);
        else
            search(t->left,t, a);
    }
    else
    {
        if(t->right == nullptr)
            return make_tuple(nullptr, nullptr);
        else
            search(t->right,t, a);
    }
}

int main()
{
    //(Make binary tree out of array elements).
    int arr[6]= {10,5,15,3,7,18};
    root -> val = arr[0];
    for(int i=1;i<6;i++)
    {
        insert(root ,arr[i]);
    }
    //add some more element.
    insert(root, 12);
    insert(root, 11);
    insert(root, 13);
    insert(root, 14);   

    //search element in tree.
    node* mynode; node* parent;
    tie(mynode, parent) = search(root, nullptr, 10);
    
    mynode ? cout << "yes" : cout << "no";
    mynode = nullptr;
    tie(mynode, parent) = search(root, nullptr, 22);  //(nullptr,nullptr) outcome from search, mynode here is nullptr which is correct what I should be.
    
    mynode ? cout << "yes" : cout << "no";              // My code should be a nullptr here but it is not.
    /* In the line above, mynode have the value what it was at line 92. Why? */
}
```

Here, at my local PC, the output is '''yesyes''', even if 22 is not present in the binary search tree.   

Debugging didn't help me much. Just helped me driving the comments written above.


When the above code was run at [http://cpp.sh/8hreo](http://cpp.sh/8hreo), it gives correct output that is '''yesno'''.

Only God may now know why PC gives wrong answer.   
Is it hardware problem or GCC should be updated.   
