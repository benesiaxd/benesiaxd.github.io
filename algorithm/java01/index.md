---
layout: post
author: "Kwon Yool"
title:  "세 정수중에 두번째로 큰 정수 출력하기."
subtitle: "JAVA 알고리즘 문제 - 01"
type: "JAVA"
algorithm: true
text: true
ridi: true
portfolio: true
post-header: true
header-img: "img/card.jpg"
main-img: "img/algorithm.jpg"
role-title: "학부생"
role-specific: ""
team: "본인"
platforms: "Eclipse"
date: "Dec 2019"
order: 1
---
## 문제 : 세 정수 A, B, C가 주어진다. 이때, 두 번째로 큰 정수를 출력하는 프로그램을 작성하시오.

<br/>



#### 입력
```
첫째 줄에 세 정수 A, B, C가 공백으로 구분되어 주어진다. (1 ≤ A, B, C ≤ 100)
```

#### 출력
```
두 번째로 큰 정수를 출력한다.
```
<br/>
<br/>

#### 테스트케이스
```
20 30 10     20
30 30 10     30
40 40 40     40
20 10 10     10
```
<br/>
해설 : 배열을 정렬하는것을 떠올린다면 매우 쉬운 문제이다.
<br/>

_ _ _

{% highlight JAVA %}
import java.util.Scanner;
import java.util.Arrays;
class Example{
	public static void main(String[] arg) {
		Scanner sc = new Scanner(System.in);
		String nt = sc.nextLine();
		String[] sarr = nt.split(" ");
		int[] arr = new int[3];

		for(int i=0; i<3; ++i)
			arr[i] = Integer.parseInt(sarr[i]);
	
		Arrays.sort(arr);  // Arrays클래스의 정렬 메쏘드
		System.out.println(arr[1]);
	}
}
{% endhighlight %}

<br/>

크게 어려운건 없었다. 이런 쉬운거에서 막히면 난감하니 이런 기본적인 것들을 자주 봐서 눈에 익혀놔야 겠다.
