
# . Prediction


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

1. linked list만들 때, head 없고 next만 있음. 
Singly LinkedList 정석 구현 찾아보면,
LinkedList 라는 클래스 안에 Node라는 sub class만들고,
Node안에 data, next;있음

LinkedList class안에는 Node head, tail 있는 식.

2. add();에서 보면,
Node 객체 new로 만들어서 넣어야 하는 부분 빼먹음
또한 정석 구현에서, head, tail이 있으니까, 굳이 내가 구현한 것 처럼, while문으로 끝까지 안가도, 바로 tail.next = node 해서 붙일 수 있음.





## b. things I couldnt find

코드에 주석달아놓음.

그 외에 눈여길 점은, UI와 database의 분리임.


### 1. UI

flush\_stdin();
PrintUI();



### 2. database 


File 관련

DATA\_FILE\_NAME
LoadList();
SaveList();
ReleaseList();



Database 관련

\_USERDATA
\*FindNode();
AddNewNode();
Add();
Search();
PrintAll();
RemoveNode();
Remove();



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
