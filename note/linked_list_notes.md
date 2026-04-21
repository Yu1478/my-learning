# 📘 数据结构与算法 —— 链表经典题整理（C语言）

---

## 🧩 1. 合并两个有序链表
### 思路
- 哨兵节点
- 双指针合并

```c
Node* merge(Node* L1, Node* L2){
    Node L3;
    L3.next = NULL;
    Node* p = &L3;

    while(L1 && L2){
        if(L1->data <= L2->data){
            p->next = L1;
            L1 = L1->next;
        } else {
            p->next = L2;
            L2 = L2->next;
        }
        p = p->next;
    }

    p->next = L1 ? L1 : L2;
    return L3.next;
}
```

---

## 🧩 2. 删除排序链表中的重复元素
### 思路
- 双指针
- 删除重复节点

```c
void deletenode(Node* head){
    Node* p1 = head;
    while(p1){
        Node* p2 = p1;
        while(p2->next){
            if(p2->next->data == p1->data){
                p2->next = p2->next->next;
            } else {
                p2 = p2->next;
            }
        }
        p1 = p1->next;
    }
}
```

---

## 🧩 3. 移除链表元素
### 思路
- 哨兵节点
- 删除指定值

```c
Node*deleteelem(Node*head,int value){
    Node*dummy=(Node*)malloc(sizeof(Node));
    dummy->next=head;
    Node*p=dummy;
    while(p->next){
        if(p->next->data==value){
            p->next=p->next->next;
        } else p=p->next;
    }
    return dummy->next;
}
```

---

## 🧩 4. 从尾到头打印链表
### 思路
- 头插法实现反转

---

## 🧩 5. 删除区间并插入链表
### 思路
- 找区间前后
- 拼接新链表

---

## 🧩 6. 二进制链表转整数
### 思路
- 位权累加（2^i）

---

## 🧩 7. 两数相加Ⅱ
### 思路
- 转字符串
- 大数加法

---

## 🧩 8. 区间反转链表
### 思路
- 局部反转
- 三指针

---

## 🧩 9. 最大孪生和
### 思路
- 复制 + 反转
- 双指针求最大

---

## 🧩 10. 重排链表
### 思路
- 快慢指针
- 反转后半
- 交叉合并

---

## 🧩 11. 删除倒数第N个节点
### 思路
- 快慢指针

```c
for (int i = 0; i < n; i++) {
    fast = fast->next;
}
```

---

# 🚀 总结模板

## 常用技巧
- 哨兵节点（dummy）
- 快慢指针
- 三指针反转
- 头插法
- 双指针遍历

---

📌 适合：
- 期末复习
- 面试刷题
- GitHub 项目整理
