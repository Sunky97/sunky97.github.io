---
title:  "[프로그래머스] 스킬트리"
excerpt: ""

categories:
  - programmers
tags:
  - [Coding Test, Algorithm, Summer/Winter Coding(~2018), stack/queue]

toc: true
toc_sticky: true
 
date: 2021-04-02
last_modified_at: 2021-04-02
---


# **문제**

문제 링크 : <https://programmers.co.kr/learn/courses/30/lessons/49993>

<br>
<br>
<br>
<br>

# **코드**

```javascript
function solution(skill, skill_trees) {
    var answer = 0;
    
    for(let i=0; i<skill_trees.length; i++){
        
        let queue = skill.split('');
        let check = true;
        for(let x of skill_trees[i]){
            if(queue.includes(x)){
                if(x!==queue.shift()) check = false;
            }
        }
        
        if(check) answer++;
    }
    return answer;
}
```

<br>

## **풀이**
선행스킬의 배열 `queue` 를 만들어놓고 `skill_trees` 의 요소를 for 루프 돌면서
`queue` 에 포함되어있는 스킬이면 `queue` 를 `shift()` 한다. 그때 shift 한 요소가 x 와 다르면 `check` 를 `false` 로 바꿔주었다.
선행스킬 순서와 스킬트리가 가능하다면 answer 에 +1 해줌.