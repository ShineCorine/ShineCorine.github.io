---
layout: single
title:  "리액티브 프로그래밍"
categories: "기술세미나"
tag: [Kerenel360, 기술세미나, 리액터, 스프링]
---


### 리액티브 프로그래밍

비동기, 논 블로킹
논 블로킹: 2번 라인에서 실행 한 일 때문에 3번 라인을 실행 하지 못하면 블로킹 된 상태.

리액티브 프로그래밍은 비동기와 논 블로킹이라는 기둥위에 새워짐.

리액티브 스트림

Reactor3, Rxjava 2, Akka Streams, Vertex_x , Ratpack은 interoperable하다

역압력

리액티브 스트림 시퀀스에서 퍼블리셔는 데이터를 생산합니다. 그러나 아무것도 하지 않다가 구독자가 등록 하면 데이터를 푸쉬합니다.

subscriber의 처리 능력을 넘어서 publisher가 데이터를 push하면 데이터가 유실되거나 기타 다른 문제가 생길 수 있다. 때문에 역압력(back pressure) 개념이 중요한다.

역 압력은 subscriber가 publisher에게 feedback을 줘서 publisher가 push하는 속도를 조절하는 것을 말합니다.

리액터는 operator라는개념을 도입했다.
