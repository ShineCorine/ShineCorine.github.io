---
layout: single
title:  "red-black-tree"
categories: "알고리즘"
tag: [알고리즘, 트리, 정렬]
---

# 레드 블랙 트리
이진 탐색 트리에 추가적으로 색을 나타내는 비트를 더하여 검은 색과 빨간 색을 나타낸 트리

## 레드 블랙 트리의 특성
1. 모든 노드는 black 혹은 red이다.
2. root 노드는 black
3. leaf node(nil) 는 bloack
4. red인 노드는 red인 자식 노드를 가질 수 없다( red는 경로상에 연속으로 나올 수 없다)
5. 모든 root에서 leaf 로 이어지는 경로들의 black의 수는 같다.

# 레드 블랙 트리의 회전

## 회전의 종류
left와 right  회전이 있다.
### left 회전
특정 노드 x가 자식 노드(x의 right, nil이 아님)의 left로 변경되는 것을 말한다.
```
LEFT-ROTATE(T, x)
y = x.right;
x.right  y.left;

if(y.left != T.nil)
    y.left.p = x.p
x.p = x.p
if(x.p == T.nil)
    T.root = y
else if (x == x.p.left) // x가 부모의 left일 때
    x.p.left = y
else x.p.right = y
y.left = x
x.p = y
```


### right 회전
특정 노드 x가 x의 left자식노드(nil이 아님)의 right 자식노드로 변경되는 것을 말한다.
```
RIGHT-ROTATE(T, x)
y = x.left;
x.left = y.right;
if(y.right != T.nil)
    y.right.p = x;
if(x.p == T.nill)
    T.root = y;
else if(x==x.p.right)
    x.p.right = y;
else
    x.p.left = y;
```


## 삽입
1. node를 insert하고 red로 칠한다
```
PB-INSERT(T, z)
y = T.nil
x = T.root
while x!= T.nil
    y = x
    if z.key <  x.key
        x = x.left
    else    
        
        x = x.right
z.p = y
if y == T.nil
    T.root = z
else if z.key < y.key
    y.left = z
else y.right = z
z.left = T.nil
z.right = T.nil
z.color = RED
RB-INSERT-FIXUP(T, z)

```