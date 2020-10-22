---
description: JavaScript 공부
---

# JavaScript

JavaScript 공부 자료

# if, for example

## for

```js
var hometown = [
	{ name: '강감찬', place: '대구', city: '고양' },
	{ name: '이순신', place: '서울' },
	{ name: '이몽룡', place: '부산', city: '경상도' },
];

for ( var i = 0; i < hometown.length; i++ ) {
	var h = hometown[i];

	if ( !h || !h.city ) continue;

	// console.log(h.city);

	if ( h.name == '이몽룡' ) {
		console.log(h.name + '의 고향은 ' + h.place + ' ' + h.city + '입니다.');
		break;
	}
}
```

## forEach

```js
var data = [1, 2, null, undefined, NaN, ""];

data.forEach(function(value) {
  console.log(value);
})
```

## for in

- for in은 Array에서 사용하지 않아야 한다.
- 의도하지 않은 것까지 읽어 올 우려가 있다.

```js
var hometown = {name: '이몽룡', place: '부산', city: '경상도'};

for ( let item in hometown ) {
	if (!hometown.hasOwnProperty(item)) continue;
	console.log(item + ' ' + hometown[item]);
}
```

```js
var data = [1, 2, null, undefined, NaN, ""];

Array.prototype.getIndex =  function(){}; // for in에서는 표시됨

for (let i in data) {
  console.log(i);
}
```

## for of

```js
var data = [1, 2, null, undefined, NaN, ""];

Array.prototype.getIndex =  function(){}; // for of에서는 표시되지 않음

for (let i of data) {
  console.log(i);
}
```

## switch

```js
var subject = 'JavaScript';

switch (subject) {
	case 'C++':
		console.log('초보자를 위한 C++책');
		break;
	case 'JavaScript':
		console.log('초보자를 위한 JavaScript책');
		break;
	case 'Python':
		console.log('초보자를 위한 Python책');
		break;
	case 'JAVA':
		console.log('초보자를 위한 JAVA책');
		break;
	default:
		console.log('난 초보자가 아니야!');
		break;
}
```


## while

```js
var hometown = [
  { name: '감찬', city: '고양' },
  { name: '순신', place: '서울', city: '경기도' },
  { name: '몽룡', place: '부산', city: '경상도' },
];


var isHometown = function(h, name) {
  console.log(`함수실행. ${h.city} 도시에서 ${name}을 찾습니다.`);

  if (h.name === name) {
    console.log(`${h.name}의 고향은 ${h.city} ${h.place} 입니다.`);
    return true;
  }
  return false;
}

var h;
while (h = hometown.shift()) { //shift: 배열의 앞에서부터 값을 하나씩 빼내오는 함수
  if (!h.name || !h.place || !h.city) continue;
  
  var result = isHometown(h, '몽룡');
  if (result) break;
}

var i = 0;
var names = ['남준', '정국', '호석', '윤기'];
var cities = ['경기', '부산', '대구', '광주'];
do {
  hometown[i] = { name: names[i], city: cities[i]};
  i++;
} while (i < 4);

console.log(hometown);
```

