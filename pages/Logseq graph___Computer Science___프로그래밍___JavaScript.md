deck:: 🌐 Logseq graph/📂 Computer Science/📂 프로그래밍/📖 JavaScript

- 다음 코드의 출력 결과는? #card 
  id:: 678f38f4-0456-4465-8a50-025a5f57d830
  ```javascript
  const numbers = [1, 2, 3]	
  const result = numbers.map(number => number * 2)
  console.log(result) // result = ?
  ```
	- ```
	  Array [2, 4, 6]
	  ```
- 다음 코드에서 배열의 map() 함수를 사용하여 `items` 배열을 [1, 2, 3]으로 변환하는 방법은? #card
  ```javascript
  const items = [{ no: 1 }, { no: 2 }, { no: 3}]
  const result = // ?
  console.log(result) // [1, 2, 3]
  ```
	- ```javascript
	  const items = [{ no: 1 }, { no: 2 }, { no: 3}]
	  const result = items.map(item => item.no)
	  console.log(result) // [1, 2, 3]
	  ```