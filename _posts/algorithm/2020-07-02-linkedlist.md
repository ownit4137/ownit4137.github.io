---
layout: post
title: Linked List
categories: [Algorithm]
hide_last_modified: true
---

# Linked List

Implementing a Linked List in C++
{:.faded}

![](/assets/img/post/algorithm/86223188.png)

https://www.faceprep.in/data-structures/linked-list-introduction/
{:.figcaption}


## Singly Linked List


### class Node

- Node(int e) : e값을 가지는 Node 생성

~~~cpp
class Node {
public:
	Node(int e) {
		elem = e;
		this->next = NULL;
	}
private:
	int elem;
	Node* next;

	friend class SLinkedList;  //friend
};
~~~

### class SLinkedList

- addFront(int x) : newNode 생성 -> 연결
- addBack(int x) : newNode 생성 -> 연결
- removeFront() : head 노드를 old 노드에 복사 -> 연결 끊기 -> delete
- front() : return head->elem;
- empty() : return head==NULL;
- showList() : do traverse using cur pointer

~~~cpp
class SLinkedList {
private:
	Node* head;
	Node* tail;
public:
	SLinkedList() :head{ NULL }, tail{ NULL } {}

	void addFront(int x) {
		Node* newNode = new Node(x);
		if (empty()) head = tail = newNode;
		else {
			newNode->next = head;
			head = newNode;
		}
	}
	void addBack(int x) {
		Node* newNode = new Node(x);
		if (empty()) head = tail = newNode;
		else {
			tail->next = newNode;
			tail = newNode;
		}
	}
	int removeFront() {
		if (empty()) return -1;
		Node* old = head;
		head = old->next;
		int oldelem = old->elem;
		delete old;
		return oldelem;
	}
	int front() {
		if (empty()) return -1;
		return head->elem;
	}
	int empty() { return head == NULL; }
	void showList() {
		if (empty()) { cout << -1; return; }
		for (Node* cur = head; cur != NULL; cur = cur->next) {
			cout << cur->elem << " ";
		}
	}
};
~~~

## Doubly Linked List

## Circular Linked List

### class Node

~~~cpp
class Node {
public:
	Node(int e) {
		elem = e;
		this->next = NULL;
	}
private:
	int elem;
	Node* next;

	friend class CLinkedList;
};
~~~


### class CLinkedList

- addFront() : newNode 생성 -> 연결
- addBack() : newNode 생성 -> 연결
- remove(int idx) : 삭제할 노드와 **그 전 노드** 를 가리킴 -> head/tail 갱신 -> 연결 -> 삭제
- showList() : do traverse, p가 tail이면 반복문 종료

~~~cpp
class CLinkedList {
public:
	CLinkedList() {
		head = NULL;
		tail = NULL;
	}
	void addFront(int x) {
		Node* newNode = new Node(x);
		if (empty()) {
			head = newNode;
			tail = newNode;
			newNode->next = head;
		}
		else {
			newNode->next = head;
			tail->next = newNode;
			head = newNode;
		}
	}
	void addBack(int x) {
		Node* newNode = new Node(x);
		if (empty()) {
			head = newNode;
			tail = newNode;
			newNode->next = head;
		}
		else {
			newNode->next = head;
			tail->next = newNode;
			tail = newNode;
		}
	}
	void remove(int idx) {
		Node* old = head;
		Node* prev = tail;
		for (int id = 0; id < idx; id++) {
			old = old->next;
			prev = prev->next;
		}
		if (old == head) head = old->next;
		if (old == tail) tail = prev;
		prev->next = old->next;
		delete old;
	}
	void showList() {
		for (Node* p = head;; p = p->next) {
			cout << p->elem << " ";
			if (p == tail) break;
		}
	}
	int empty() { return head == NULL; }
private:
	Node* head;
	Node* tail;
};
~~~



삽입을 구현할 때, 빈 리스트(head == NULL or tail == NULL)는 따로 처리
{:.note}
