---
layout: single
title:  "Algorithm BOJ 구간합 구하기(1) 11659"
categories: algorithm
tag: [Java, algorithm, BOJ, 백준, 구간합 구하기, 자료구조, 수학, 백준11659]
toc: true
author_profile: false
sidebar:
    nav: "docs"
---
## BOJ 구간합 구하기-1
[https://www.acmicpc.net/problem/11659](https://www.acmicpc.net/problem/11659)

### 문제
![구간합 구하기](/assets/img/BOJ11659.jpg)

### 풀이
<li>N개의 수를 입력받으며 동시에 합배열 arr1[i] = arr1[i - 1] + arr2[i] 생성</li>
<li>구간합 arr[a] - arr[b - 1]로 결과 출력</li>

### 코드구현
```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.StringTokenizer;

public class Main {
    public static void main (String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        StringTokenizer st = new StringTokenizer(br.readLine());

        int N = Integer.parseInt(st.nextToken());
        int M = Integer.parseInt(st.nextToken());

        st = new StringTokenizer(br.readLine());
        long[] arr = new long[N + 1];
        arr[0] = 0;

        for (int i = 1; i <= N; i++) {
            arr[i] = arr[i - 1] + Integer.parseInt(st.nextToken());
        }

        for (int i = 0; i < M; i++) {
            st = new StringTokenizer(br.readLine());
            int a = Integer.parseInt(st.nextToken());
            int b = Integer.parseInt(st.nextToken());
            System.out.println(arr[b] - arr[a - 1]);
        }
    }
}
```
