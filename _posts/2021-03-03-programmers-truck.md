---
title:  "[프로그래머스] 다리를 지나는 트럭"
excerpt: ""

categories:
  - programmers
tags:
  - [Coding Test, Algorithm, stack/queue]

toc: true
toc_sticky: true
 
date: 2021-03-30
last_modified_at: 2021-03-30
---


# **문제**

문제 링크 : <https://programmers.co.kr/learn/courses/30/lessons/42583?language=javascript>

<br>
<br>
<br>
<br>

# **코드**

```javascript
function solution(bridge_length, weight, truck_weights) {
    
    let time = 1;
    //다리
    let queue = Array.from({length:bridge_length-1},v => 0);
    //현재무게
    let cw = truck_weights.shift();
    queue.push(cw);
    
    //현재 무게가 0 이라는 것은 남은 트럭이 없다는 뜻
    while(cw!==0){

        //현재 무게에서 다리에서 shift 한 값을 빼줌
        cw -= queue.shift();
        
        //현재무게, 다음트럭의 무게를 더했을때 최대 무게보다 작다면 
        if(cw+truck_weights[0]<=weight){
            let truck =truck_weights.shift();
            //다리의 맨 끝에 트럭을 푸시해줌
            queue.push(truck);
            //현재무게 = 현재무게 + 트럭의 무게
            cw += truck;
        }else{
            //최대 무게가 넘는다면 0 을 집어넣음, 아무것도 없다는 의미
            queue.push(0);
        }
        time++;
    }
    
    return time;
}
```

<br>

## **소감**
처음에 `while`문 조건을 `truck_weights.length` 로 잡았는데  
그러면 `shift()` 만 몇 번하면 끝난다는 생각을 못 했다. . .
그래서 변수 `time` 을 1 로잡고 이미 트럭한대가 올라가 있는 상황에서 모든 트럭이 지나가면 무게가 0 이 된다는 조건으로 다시 코드를 짜니까 성공 !
