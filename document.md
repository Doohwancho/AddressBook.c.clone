
# A. Prediction


## a. general idea

goal: linked list database in c

function
1. add
2. search
3. print all
4. remove
5. exit


## b. function.add

### 1. build a singly linked list

class Node {

	Node head;
	Node next;

	String name;
	String phoneNumber;

	Node(){
		this = head;
		head.next = NULL;
	}
	
}

Node head = new Node();


Q. c는 camel case로 안쓰고 snake case로 쓰지 않나?





### 2. how to add a node in a singly linked list?


function void add(Node node, String name){
	Node tmp = head;
	while(tmp.next != NULL){
		tmp = tmp.next;
	}
	tmp.next = node;
	tmp = tmp.next;
	tmp.next = NULL;
}


## c. function.search

function Node search(String name){

	Node tmp = head;
	while(tmp != NULL && tmp.name != name){
		tmp = tmp.next;
	}
	if(tmp != NULL){
		print(tmp.name);
		print(tmp.phoneNumber);
	}

}



## d. function.print all

function void printAll(){
	Node tmp = head;
	while(tmp != NULL){
		print(tmp.name);
		print(tmp.phoneNumber);
		tmp = tmp.next;
	}
}

## e. function.remove

function void remove(String name){
	Node tmp = head;
	Node prev = tmp;

	while(tmp != NULL && tmp.name != name){
		prev = tmp;
		tmp = tmp.next;
	}
	if(tmp != NULL){
		prev.next = tmp.next;
		free(tmp);
	}
}


Q. free(tmp); 맞나?

## f. function.exit

free memory 한 다음,
break하는 함수 썼을 것 같다.

Q. c에서 break 하는 함수뭐쓰지




# B. Analyze

## a. correct wrongly predicted


## b. things I couldnt find




---
level2. binary search tree로 구현


---
level3. AVL Tree로 구현

---
level4. B Tree로 구현

조건 1. Index 개념 도입
조건 2. 10만건 데이터 select시, 성능이 일정해야 함


---
level5. implement it in c++
