---
layout: post
title: Stack & Queue
categories: [Algorithm]
hide_last_modified: true
---

![](/assets/posts/al/aafb2884.png)
https://medium.com/x-organization/stack-and-queue-60f365963552
{:.figcaption}


## Stack

Implementing Stack & Queue in C++

### class Stack(array)

- size 고정

~~~cpp
class Stack {
public:
	int arr[10000];
	int t = -1;

	int empty() {
		if (t == -1) return 1;
		return 0;
	}
	int top() {
		if (empty()) return -1;
		return arr[t];
	}
	void push(int x) {
		arr[++t] = x;
	}
	int pop() {
		if (empty()) return -1;
		return arr[t--];
	}
	int size() {
		return (t + 1);
	}
};
~~~

### class linkedStack(linkedlist)

- 만들어놓은 SLinkedList ADT를 사용
- front(head)에서 push, pop이 일어남
- n은 스택의 원소 개수를 나타냄


~~~cpp
class linkedStack {
private:
	int n;
	SLinkedList* S;
public:
	linkedStack() {
		this->S = new SLinkedList();
		this->n = 0;
	}
	int size() { return n; }
	bool empty() {
		if (size()) return false;
		else return true;
	}
	int top() {
		if (empty()) { return -1; }
		else {
			return S->front();
		}
	}
	void push(int e) {
		S->addFront(e);
		n++;
	}
	int pop() {
		if (empty()) { return -1; }
		else {
			int elem = S->front();
			S->removeFront();
			n--;
			return elem;
		}
	}
};
~~~

## Queue

### class Queue

a
