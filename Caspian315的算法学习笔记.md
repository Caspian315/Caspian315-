# Caspian315的算法学习笔记



## 双链表



双链表及其创建函数的实现

```cpp
class DoublyListNode {
public:
    int val;
    DoublyListNode *next, *prev;
    DoublyListNode(int x) : val(x), next(NULL), prev(NULL) {}
};

DoublyListNode* createDoublyLinkedList(const vector<int>& arr) {
    if (arr.empty()) {
        return NULL;
    }
    DoublyListNode* head = new DoublyListNode(arr[0]);
    DoublyListNode* cur = head;
    // for 循环迭代创建双链表
    for (int i = 1; i < arr.size(); i++) {
        DoublyListNode* newNode = new DoublyListNode(arr[i]);
        cur->next = newNode;
        newNode->prev = cur;
        cur = cur->next;
    }
    return head;
}

```



接下来实现双链表的四大基本功能---增删改查

### 查/改

从头结点或尾节点开始，根据需要向前或向后遍历

```cpp
DoublyListNode* head = createDoublyLinkedList({1,2,3,4,5});
DoublyListNode* tail;

//从头向后
for(DoublyListNode* p = head; p != nullptr; p = p ->next){
//查或改 
    std::cout <<p -> val <<std::endl;
    tail = p;
}

//从尾向前
for(DoublyListNode* p = tail ; p != nullptr;p = p ->prev){
	std::cout<<p -> val <<std::end;
}
```

根据索引靠近头部还是尾部选择其中一种方式



### 增



头部插入一个元素

```cpp
DoublyListNode* head = createDoublyLinkedList({1,2,3,4,5});

DoublyListNode* newHead = new DoublyListNode(0);
newHead -> next = head;
head -> prev = newHead;
head = newHead;
```



尾部插入一个元素

```cpp

```

