---
layout: post
title: Functional Concept
date: 2017-11-14
categories: Functional Programming
---

* content
{:toc}

## Closure
- function안에 function이 있을 때 외부 function의 지역변수를 내부 function이 참조한다면, 내부 function의 실행이 끝나기 전까지 외부 function이 종료되었더라도 변수를 capture하고 있다.
- 쉽게말해 function이 function을 리턴할때 클로저가 발생한다. 라고 말하면 쉬울듯
- 리턴되는 코드블록을 closure. 리턴되는 코드블록의 모든 context는 유지된다. capture상태로
- 함수의 실행을 지연시킨다. 인자로 특정 변수를 고정시켜놓고 함수 변수로 갖고 있다가 나중에 실행.
- code (javascript)
```javascript
function outter(){
    var out = 'out variable';
    return function(){
        console.log(out);
    }
}

inner = outter();
inner();

function lazyFunction(num){
    return function(a){
        return a + num;
    }
}

lazy = lazyFunction(3);     // a + num의 num을 3으로 고정
lazy(4);                    // 4 + 3
lazy(5);                    // 5 + 3
```
***
- 위와같은 코드를 본다면 inner함수는 outter의 지역변수 out을 참조하고있다. outter함수는 실행을 마치고 return함수를 반환하여 실행이 종료되지만 return하는 함수가 outter의 지역변수를 참조하기 때문에 inner함수가 종료되기 전까지 outter함수는 소멸되지 않고 유지된다. 이를 closure라고 한다.

## Currying
- 함수의 인수의 개수를 조작하는데 쓰인다. 