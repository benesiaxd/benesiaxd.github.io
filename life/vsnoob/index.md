---
layout: post
title: "Visual Studio 2019를 사용해보자"
subtitle: "IDE와 친해지자!"
type: "Visual Studio IDE"
life: true
text: true
author: "Kwon Yool"
post-header: true
header-img: ""
date: "Jan 2020"
order: 1
draft: true
---
# Visual Studio 2019 구조 이해하기

앞으로 프로젝트를 진행하거나 미래에 Visual Studio IDE를 사용할 일이 있을거 같기때문에

Visual Studio에 대해서 공부해보았다.

**프로젝트(Project)**는 컴파일의 결과물로 하나의 실행파일 혹은 라이블러리 등을 만들어내는, 말 그대로 **하나의 프로그램을 만드는 묶음** 입니다.



그렇다면 솔루션은? **솔루션(Solution)은 하나이상의 프로젝트가 모인 집합** 이라고 볼 수 있습니다.

왜 여러 개의 프로젝트를 같이 모을 생각을 하게 된걸까요??

보통 특정 회사에서 누군가에게 “솔루션”을 제공한다는 것은 **하나 이상의 제품을 한 번에 제공**한다는 의미입니다. 프로그래밍 측면에서도 그렇습니다. 소형 프로젝트가 아닌 이상 여러 개의 실행 파일과 라이브러리를 만들어야 하는 것이 보통이며, 이것을 묶어 하나의 “솔루션”으로 관리하는 것이 여러 방면에서 이득이 될 수 있습니다.



## 1. Project 생성

