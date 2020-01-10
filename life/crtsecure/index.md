---
layout: post
title: "Visual Studio 에서 _CRT_SECURE_NO_WARNINGS 해결방안"
subtitle: "IDE와 친해지자!"
type: "Visual Studio IDE"
life: true
text: true
author: "Kwon Yool"
post-header: true
header-img: "img/Errorimg.jpg"
date: "Jan 2020"
order: 2
---


<img src="img\Errorimg.jpg" alt="Errorimg" style="zoom:150%;" />

위 에러는 strcpy() 등의 함수를 사용할때 자주 볼 수 있다. 😡

*Stack Overflow*  취약점이 밝혀진 함수이기 때문에 IDE에서 사전에 에러를 띄워주어 다른함수를 사용하게 유도하는 것인데

[^Stack Overflow]: 할당된 메모리 이상을 덮어쓰게 되어 다른 메모리공간을 침범하여 프로그래머가 의도치 않은 일이 일어날수 있는 버그.

strcpy_s() 함수를 사용하는 대안이 있지만 공부하는 입장에서 매우 방해된다.

####  😀 해결 방법

1. SDL 설정을 꺼주는 방법. (내가 사용한 방법 🤗)

2. 전처리기를 설정



#### 1. SDL 검사를 꺼주는 방법. (내가 사용한 방법 🤗)

![1](img\1.jpg)

![2](img\2.jpg)



#### 2. 전처리기 설정

소스코드 상단에

{% highlight cpp %}

#define CRT_SECURE_NO_WARNINGS

{% endhighlight %}

를 추가해주면 됩니다.

