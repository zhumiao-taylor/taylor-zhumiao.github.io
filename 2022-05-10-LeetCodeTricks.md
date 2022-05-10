---
layout: post
title: Interview Code Tricks
subtitle: Interviewing Needs Tricks.
tags: [leetcode]
---

# Binary Search
**Search For a Given Target In a Sorted Array.**
```Python
def binary_search():
    l, r = 0, len(arr)-1
    while l <= r:
        mid = (l+r) // 2
        cur = array[mid]
        if cur == target:
            return mid
        elif cur < target:
            l = mid + 1
        else:
            r = mid + 1
    return -1
```

**Search For a Boundary In a Solution Set Splited By a Property.**
```Python
def binary_search():
    l = left_bound - 1
    r = right_bound + 1
    while l + 1 < r:
        mid = (l+r) // 2
        if satisfyLeftProp(mid):
            l = mid
        else:
            r = mid

    if satisfyLeftProp(mid):
        return l
    return r
```
--------------

# DFS
**Pure DFS**
```Python
def dfs(v):
    visited[v] = true
    for w in v's neighbors:
        if not visited[w]:
            dfs(w)
```
--------------

# BackTrack
**BackTrack = DFS + State Reset + Prune**
```Python
def backtrack(search_set, recursive_level, cur_state..., result_set):
    
    if recursive_level >= end_level:
        print or add cur_state to result_set
        return

    for reachable branch paths:
        
        if prune(recursive_level, cur_state...):
            continue

        update(cur_state...)
   
        backtrack(search_set, recursive_level+1, cur_state..., result_set)

        reset(cur_state...)
```

--------------

# BFS
**No Need to Know Which Level being Traversed at**
```Python
while queue not empty:
    cur = queue.pop()
    if cur is valid and not visited:
        process()
    for node in cur's neighbor nodes:
        if node is valid:
            queue.push(node)
```

**Need to Know Which Level being Traversed at**
```Python
level = 0
while queue not empty:
    size = queue.size()
    while size --:
        cur = queue.pop()
        if cur is valid and not visited:
            process()
        for node in cur's neighbor nodes:
            if node is valid:
                queue.push(node)
    level++
```

--------------

# Binary Tree Traverse
