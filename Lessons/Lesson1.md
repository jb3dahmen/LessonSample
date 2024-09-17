# Linked List Fundamentals


## Why you should know this

Linked Lists are a fundamental linear data structure that stores a collection of elements. 

By understanding linked lists you will be able to exercise your ability to compare and contrast data structures.

You will also practice using programming fundamentals and object oriented programming to construct a basic linked list structure.


## Learning Objectives

1. Define a linked list
1. Implement a basic linked list structure
1. Describe how a linked list is structured in physical memory

## Prerequisite Knowledge

1. Array fundamentals & memory addresses
1. Abstract data types
1. Python programming fundamentals
1. Object oriented programming fundamentals


## What is a Linked List

### Review of Arrays (optional)

Like an array, a linked list is a linear data structure. Linear data structures are used to organize information in a sequential manner. Arrays and linked lists both implement the List abstract data type. Any data structure that implements a list can store information that is similar to a list you might use in real life. 


<img src="https://github.com/jb3dahmen/LessonSample/blob/main/Lessons/Images/list.jpg" alt="a grocery list with three grocery items" width="400"/>


We learned previously that the information stored in an array is contiguous in memory, which is a fancy way of saying the information is stored right next to each other in physical memory, a lot like a row of storage lockers. 

This property of arrays makes it easy to access information quickly using basic arithmetic. However, we found that in order to maintain the contiguous property of arrays we need to do a lot of shuffling around when we make certain modifications to the array like inserting or deleting, which can be expensive in terms of time.

### Linked Lists to the Rescue

That's where linked lists come in! The items in Linked lists are **not** placed contiguously in memory which makes them more efficient in terms of time for insert and delete operations, instead of filling in gaps and moving multiple things around we can easily rearrange the links between items which you will learn is much faster.

You can think of a linked list being arranged in memory a little bit like a scavenger hunt.

<img src="https://github.com/jb3dahmen/LessonSample/blob/main/Lessons/Images/scavengerhunt.jpg" alt="a scavenger hunt with four locations" width="600"/>

In a basic singly list which is what we will focus on in this lesson, we are always given access to the start of the linked list using a reference that is typically called the `head`. Going back to our scavenger hunt analogy the head is like the first clue of the game. 

You cannot access any of the other clues/locations without first having the first clue. To get to subsequent clues and locations you need to keep following the next clue and visit each scavenger hunt location one by one. Skipping ahead or staring in the middle is cheating!

Linked lists behave in much the same way in how they are constructed in physical memory. The items of a linked list can be stored anywhere in memory, they aren't all located right next to each other. You have to start with the head and you can only visit each item in the linked list one by one by following the links to the next item, **there's no indexing into the middle of the list like in an array!**


### Linked List Building Blocks

Let's go back to our scavenger hunt analogy. Let's pretend that each location of the hunt has a prize, this is the `data` we are going to store in our list. Each location also has a clue, this is a clue or pointer to the `next` location. 

Linked lists are typically composed of small units called `Nodes` that store both `data` and a `next` pointer, or a reference to the next node in the sequence. 

<img src="https://github.com/jb3dahmen/LessonSample/blob/main/Lessons/Images/scavengerhunt_ll.jpg" alt="a scavenger hunt with four locations showing parallel to node and next" width="600"/>

In this lesson we are going to create a node using an object oriented approach by making a Node class.

In the next section we will practice implementing a linked list using the concepts and vocabulary above. Before you begin, check your conceptual understanding using [this short quiz](https://forms.gle/PqCFmv6uLm5VMFin8).

## Implementing a Linked List

You can either watch [this video version of the implementation](https://www.youtube.com/watch?v=jQ9b6bFhYdg) or you can follow along with the text version with code snippets below. 

The fundamental building block of a linked list is a `Node`. Here we create a node class, this class has two properties called `data` and `next`. Data will be initialized when we instantiate `Node` object using it's constructor. `next` is always initialized as   `None` by default upon initialization because we haven't hooked it up to any other `Node` yet! (Consequently our last node's next will always point to None).

 <iframe frameborder="0" width="100%" height="500px" src="https://replit.com/@jesslemur/LinkedListNode?lite=true"></iframe>


To see how we can start hooking up the links between nodes, let's create three node objects that each store an integer for their data. Our goal is to build a linked list that looks like this: 

`15 -> 20 -> 35 -> None`

with the node that stores 15 being the `head` of the linked list.

To hook up nodes in our linked list we can make use of variable assignment! let's first create a head variable and to "point" it at the first node we can assign `node1` to it. 

To hook up `node2` to be the next node in the sequence we can assign the head's `next` ptr to node 2. And to hook up node3 to node2 we can do something similar.

  <iframe frameborder="0" width="100%" height="500px" src="https://replit.com/@jesslemur/LinkedListConstruct?lite=true"></iframe>


 Now that we have built a basic working linked list, complete with links, how can we access each item and print the data and look at what's there? 
 
 You may be tempted to use each of the node variables directly and print them all out, that works for this small example, but let's think ahead a little but more. How could we write code that would work for any size linked list where we don't have to deal with a bunch of separate node variables and only have access to the head?

 We can use variable reassignment again! One common pattern to traverse a linked list is to create a `temporary variable` whose job it is to just hold the current node we are looking. We can start by assigning it the head and then move it to the next node in the sequence using the next ptr. We combine this with a while loop to keep repeating this step, moving link by link until we are at the end of the list, meaning the next node is  `None`. 

 <iframe frameborder="0" width="100%" height="500px" src="https://replit.com/@jesslemur/LinkedListTraverse?lite=true"></iframe>


## Wrap Up

- In this lesson we learned about the basics of linked lists:
- What a linked list is an how it compares to arrays
- How to implement a basic linked list in Python

## What's Next

1. Linked List Methods: `append(), print_list(), delete(), insert(), is_empty()`
2. Doubly Linked Lists
