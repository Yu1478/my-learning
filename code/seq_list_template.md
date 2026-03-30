# 顺序表固定模板（C语言）

## 一、基础结构
```c
#include <stdio.h>
#define MaxList 100

typedef struct {
    int elem[MaxList];
    int length;
} L;
```

## 二、输入
```c
void inputList(L *A){
    int x;
    A->length = 0;
    while(1){
        scanf("%d", &x);
        if(x == 0) break;
        A->elem[A->length++] = x;
    }
}
```

## 三、查找
```c
int find(L *A, int e){
    for(int i = 0; i < A->length; i++){
        if(A->elem[i] == e) return 1;
    }
    return 0;
}
```

## 四、插入
```c
void insert(L *A, int e){
    if(A->length < MaxList){
        A->elem[A->length++] = e;
    }
}
```

## 五、删除
```c
void delete(L *A, int e){
    for(int i = 0; i < A->length; i++){
        if(A->elem[i] == e){
            for(int j = i; j < A->length - 1; j++){
                A->elem[j] = A->elem[j+1];
            }
            A->length--;
            return;
        }
    }
}
```

## 六、集合合并
```c
void merge(L *A, L *B){
    for(int i = 0; i < B->length; i++){
        if(!find(A, B->elem[i])){
            insert(A, B->elem[i]);
        }
    }
}
```

## 七、输出
```c
void printList(L *A){
    for(int i = 0; i < A->length; i++){
        printf("%d ", A->elem[i]);
    }
    printf("\n");
}
```

## 八、主函数
```c
int main(){
    L A, B;
    inputList(&A);
    inputList(&B);
    merge(&A, &B);
    printList(&A);
    return 0;
}
```

## 核心记忆
1. 修改数据 → 传指针（L*）
2. 访问成员 → 用 ->
3. 遍历 → i < length
4. 插入 → elem[length++] = x
5. 查找 → find函数
