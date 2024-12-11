## [225. Implement Stack using Queues](https://leetcode.com/problems/implement-stack-using-queues/description/?envType=problem-list-v2&envId=queue&difficulty=EASY)

- 문제출처 : leetcode
- 개념 : 큐

큐를 사용해서 스택 구현해보기.

```
var MyStack = function() {
    this.q1 = [];
    this.q2 = [];
};

MyStack.prototype.push = function(x) {
    this.q2.push(x)
    while(this.q1.length){
        this.q2.push(this.q1.shift());
    }
    [this.q1,this.q2] = [this.q2,this.q1];
};


MyStack.prototype.pop = function() {
    return this.q1.shift();
};


MyStack.prototype.top = function() {
    return this.q1[0]
};


MyStack.prototype.empty = function() {
    return this.q1.length===0
};
```
![image](https://github.com/user-attachments/assets/ef03d088-931a-4345-802a-cf28f7bafa01)



push 부분이 까다로워 풀이를 참고 하였다.  
두번 풀어보았으며 완벽히 이해하였다.
