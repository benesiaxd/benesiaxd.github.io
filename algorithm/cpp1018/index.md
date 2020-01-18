---
layout: post
author: "Kwon Yool"
title:  "체스판 다시 칠하기"
subtitle: "Algorithm"
type: "C++"
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
platforms: "Visual Studio"
date: "Jan 2020"
order: 2
---
# 백준 1018번 문제(Silver V)


## 문제

------

지민이는 자신의 저택에서 MN개의 단위 정사각형으로 나누어져 있는 M*N 크기의 보드를 찾았다. 어떤 정사각형은 검은색으로 칠해져 있고, 나머지는 흰색으로 칠해져 있다. 지민이는 이 보드를 잘라서 8*8 크기의 체스판으로 만들려고 한다.

체스판은 검은색과 흰색이 번갈아서 칠해져 있어야 한다. 구체적으로, 각 칸이 검은색과 흰색 중 하나로 색칠되어 있고, 변을 공유하는 두 개의 사각형은 다른 색으로 칠해져 있어야 한다. 따라서 이 정의를 따르면 체스판을 색칠하는 경우는 두 가지뿐이다. 하나는 맨 왼쪽 위 칸이 흰색인 경우, 하나는 검은색인 경우이다.

보드가 체스판처럼 칠해져 있다는 보장이 없어서, 지민이는 8*8 크기의 체스판으로 잘라낸 후에 몇 개의 정사각형을 다시 칠해야겠다고 생각했다. 당연히 8*8 크기는 아무데서나 골라도 된다. 지민이가 다시 칠해야 하는 정사각형의 최소 개수를 구하는 프로그램을 작성하시오.
</br>

## 입력
------
첫째 줄에 N과 M이 주어진다. N과 M은 8보다 크거나 같고, 50보다 작거나 같은 자연수이다. 둘째 줄부터 N개의 줄에는 보드의 각 행의 상태가 주어진다. B는 검은색이며, W는 흰색이다.

## 출력
------
첫째 줄에 지민이가 다시 칠해야 하는 정사각형 개수의 최솟값을 출력한다.

## 예제 입력 1

```
8 8
WBWBWBWB
BWBWBWBW
WBWBWBWB
BWBBBWBW
WBWBWBWB
BWBWBWBW
WBWBWBWB
BWBWBWBW
```

## 예제 출력 1

```
1
```

## 예제 입력 2

```
10 13
BBBBBBBBWBWBW
BBBBBBBBBWBWB
BBBBBBBBWBWBW
BBBBBBBBBWBWB
BBBBBBBBWBWBW
BBBBBBBBBWBWB
BBBBBBBBWBWBW
BBBBBBBBBWBWB
WWWWWWWWWWBWB
WWWWWWWWWWBWB
```

## 예제 출력 2

```
12
```

## 나의 풀이
그냥 간단히 생각했다. 8*8 모양대로
전체 탐색을 하여 새로운 string 변수에 넣어서 함수로 해결했다.
더 나은 방법이 있겠지.
앞길이 멀다. 이게 solved.ac에 의하면
난이도 silver V 라는데.. 더 발전해야지.

{% highlight cpp %}
#include <iostream>
#include <string>
using namespace std;

int count(const string (&temp)[8]){
	int ct1=0, ct2=0;
	
	for(int i=0; i<8; ++i)
		for(int j=0; j<8; ++j)
			if(temp[i][j]!=((i+j)%2 ? 'B' : 'W'))	// 전체탐색하며 BWBW인지 확인 
				ct1++;
			else
				ct2++;
	// ct1과 ct2가 구별되어 있는 이유는 BWBW순서와 WBWB순서 둘다 해보았을때 최소를 구하기 위함. 
	return (ct1<ct2 ? ct1 : ct2);
}

int main(void)
{
	int m, n;
	int ncount = 1000, temp;
	
	/* 입력 받기 */ 
	cin >> m >> n;
	string board[m];
	for(string &i : board)
		cin >> i;
	/* --------- */


	string stemp[8];	// 8*8 체스판 임시변수  
	for(int i=0; i<=m-8; ++i)	// 8 * 8 형태로 전체 부분 탐색 
		for(int j=0; j<=n-8; ++j){	//
			for(int k=0; k<8; ++k)	// 탐색중에 8*8을 임시 stemp 변수에 저장 
				stemp[k] = board[i+k].substr(j, 8);
			temp = count(stemp);	// 함수 실행 8*8에서 바꿔야하는 최소 갯수 
			if(temp < ncount) ncount = temp; 
		}
		
	cout << ncount << endl;
	return 0;
}
{% endhighlight %}


