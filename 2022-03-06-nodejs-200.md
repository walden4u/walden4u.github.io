---
title: "Node.js 200제 "
description: "map() 함수는 배열에 있는 모든 item에 .map(함수)d의 파마미터로 받는 함수를 적용시킨 배열(array)을 리턴한다.봉급을 10%씩 올린 결과를 출력"
date: 2022-03-06T01:09:57.482Z
tags: ["JavaScript","node.js"]
---
## No.110 - map() 함수 사용하기
```
const list = [1, 2, 3];

const mutipledList = list.map(item => item * 10);
console.log(mutipledList);
mutipledList.forEach(item => console.log(item));
```
map() 함수는 배열에 있는 모든 item에 .map() 함수의 파마미터로 받는 함수를 적용시킨 배열(array)을 리턴한다.

## No.111 - map() 함수 예제
```
//define
const listEmployee = [
    { name: 'kyeongrok', age: 31, salary: 4000 },
    { name: 'jihyun', age: 31, salary: 5000 },
    { name: 'minsup', age: 35, salary: 6000 },
];

//process
const raisedSalaryList = listEmployee.map(employee => (employee.salary * 1.1));
console.log(raisedSalaryList);
raisedSalaryList.forEach(salary => console.log('salaray : %d', salary));
```
봉급을 10%씩 올린 결과를 출력

## No.112 - reduce() 함수 사용하기  

```
const scores = [10, 20, 30, 40, 50];

const sum = scores.reduce((a, b) => (a + b));
const sumWithInitValue = scores.reduce((a, b) => (a + b), 10);

console.log('sum :', sum);
console.log('sumWithInitValue :', sumWithInitValue);
```
reduce() 함수는 해당 배열의 가장 첫 번째 인덱스부터 마지막 인덱스까지의 값에 대한 누적 계산을 통해 하나의 결과를 내보내는 함수 (초기값을 추가해서 파라미터로 전달 가능)

## No.113 - reduce() 함수 예제
```
const students = [
    { name: 'kyeongrok', age: 31, score: 85 },
    { name: 'jihyun', age: 31, score: 95 },
    { name: 'minsup', age: 35, score: 76 },
];

const scores = students.map(student => student.score);
console.log(scores)

const sum = scores.reduce((a, b) => a + b, 0);
console.log('sum', sum);
```

map 함수로 데이터를 뽑아서 reduc 함수로 최종 계산
원본 데이터를 그대로 계산에 이용한다면, 데이터에 대한 복잡한 접근, 원본 데이터 손실 가능성 등 여러 문제가 있을 수 있으므로 위와 같이 map reduce를 이용하는 것이 보다 바람직함

## .filter, .map(), .reduce() 함수 예제
```
const students = [
    { name: 'kyeongrok', age: 31, score: 85 },
    { name: 'jihyun', age: 31, score: 95 },
    { name: 'minsup', age: 35, score: 76 },
];

// 점수가 80점 이상인 학생 필터링하기
const upper80StudentsSum = students.filter(student => student.score > 80).map(student => student.score).reduce((x, y) => x + y);
console.log('sum:', upper80StudentsSum);
```
filter로 배열 값을 골라낸후에 map으로 배열값에서 속성만 추출후 reduce로 최종 계산

