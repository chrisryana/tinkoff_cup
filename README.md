![image](https://user-images.githubusercontent.com/40830361/232586736-fce05b28-e7d0-417f-b88c-f503841e5a16.png)

# IT's Tinkoff Cup 2023 Frontend

https://www.tinkoff.ru/solutioncup/frontend/

_Было какое-то помутнение рассудка и я почему то не заскринила условия задач 5-12. Поэтому вспоминала их по памяти и там могут быть ошибки в описании, в вариантах ответов или может не совпадать порядок вариантов. Задания, в которых предлагаются варианты ответов, нельзя прогнать через тесты. Результаты вопросов с варианами ответов неизвестны._

[[1]](#1) [[2]](#2) [[3]](#3) [[4]](#4) [[5]](#5) [[6]](#6) [[🤷‍♀️7]](#7)

[[10]](#10) [[11]](#11) [[12]](#12) [[13]](#13) [[14]](#14) [[15]](#15)

[[16]](#16) [[17]](#17) [[18]](#18) [[19]](#19) [[20]](#20) [[21]](#21)

[[22]](#22) [[23]](#23) [[24]](#24) [[25]](#25)



<a name="1"><h3>1 ![](https://img.shields.io/badge/%D0%A1%D1%82%D0%B0%D1%82%D1%83%D1%81-%D0%9D%D0%B5%20%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BB%D0%B0%D1%81%D1%8C-orange)</h3></a>

Дано SVG-изображение размером 500 х 200. Требуется, чтобы в приложении отображалось изображение размером 60 х 25. Выберите правильный набор параметров SVG для масштабирования.

1. **`width="60" height="25" viewBox="0 0 500 200"`** ✅
2. `width="60" height="25" viewBox="500 0 200 0"`
3. `width="60" height="25" viewBox="500 200"`
4. `width="500" height="200" viewBox="60 25 0 0"`
5. `width="500" height="200" viewBox="60 0 25 0"`
6. `width="500" height="200" viewBox="60 25"`

<a name="2"><h3>2 ![](https://img.shields.io/badge/%D0%A1%D1%82%D0%B0%D1%82%D1%83%D1%81-%D0%9D%D0%B5%20%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BB%D0%B0%D1%81%D1%8C-orange)</h3></a>

У элемента заданы width и height, но если принять padding, то ширина и высота увеличиваются. Какое свойство помогает избежать этого?

1. `box-sizing: content-box;`
2. **`box-sizing: border-box;`** ✅
3. `box-sizing: initial;`

<a name="3"><h3>3 ![](https://img.shields.io/badge/%D0%A1%D1%82%D0%B0%D1%82%D1%83%D1%81-%D0%9D%D0%B5%20%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BB%D0%B0%D1%81%D1%8C-orange)</h3></a>

Даны стили и верстка:

```html
<style>
  .wrapper {
    height: 40px;
  }
  .wrapper div {
    width: 70px;
    height: 40px;
  }
  .z2 {
    z-index: 2;
    margin-bottom: -40px;
    border-right: 20px solid white;
    background: green;
  }
  .z1 {
    z-index: 1;
    margin-left: 70px;
    border-left: 20px solid black;
    background: red;
  }
</style>

<div class="wrapper">
  <div class="z2"></div>
  <div class="z1"></div>
</div>
```

Какой из этих вариантов будет отличаться внешне от других?

1. **`.z2 { position: static } .z1 { position: static }`** ✅
2. `.z2 { position: relative } .z1 { position: static }`
3. `.z2 { position: relative } .z1 { position: relative }`
4. `.z2 { position: absolute } .z1 { position: relative }`


<a name="4"><h3>4 ![](https://img.shields.io/badge/%D0%A1%D1%82%D0%B0%D1%82%D1%83%D1%81-%D0%9D%D0%B5%20%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BB%D0%B0%D1%81%D1%8C-orange)</h3></a>

Дана верстка:

```html
<div class="container">
  <div class="div2 left-section">2</div>
  <div class="div3 left-section">3</div>
  
  <div class="div4 right-section">4</div>
  <div class="div1 right-section">1</div>
  <div class="div5 right-section">5</div>
</div>
```

Фрагмент стиля:

```css
.container { width: 50em; }

.left-section { width: calc(100% - 10em); }

.right-section { width: 10em; }

.div1 { height: 7em; background-color: red; }

.div2 { height: 5em; background-color: orange; }

.div3 { height: 7em; background-color: yellow; }

.div4 { height: 5em; background-color: green; }

.div5 { height: 10em; background-color: aqua; }
```

Какие из наборов стилей дают такое расположение?

![flex](https://user-images.githubusercontent.com/40830361/232333102-2fd480a4-72b8-4680-87f5-3de45dd9b472.png)

1.
    ```css
    .container {
      display: flex;
      flex-direction: column;
      flex-wrap: wrap;
      min-height: 12em;
    }
    ```
  
2.
    ```css
    .div3:after {
      height: 10em;
    }
  
    .container {
      display: flex;
      flex-direction: column;
      flex-wrap: wrap;
      height: 22em;
    }
    ```
  
3. ✅
    ```css
    .div3 {
      margin-bottom: 7em;
    }
   
    .container {
      display: flex;
      flex-direction: column;
      flex-wrap: wrap;
      height: 22em;
    }
    ```
   
4.
    ```css
    .container {
      display: grid;
      grid-template-areas:
        "2 4"
        "3 1"
        ". 5";
    }
     
    .div1 { grid-area: 1; }
     
    .div2 { grid-area: 2; }
     
    .div3 { grid-area: 3; }
     
    .div4 { grid-area: 4; }
     
    .div5 { grid-area: 5; }
    ```
    
<a name="5"><h3>5 ![](https://img.shields.io/badge/%D0%A1%D1%82%D0%B0%D1%82%D1%83%D1%81-%D0%9D%D0%B5%20%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BB%D0%B0%D1%81%D1%8C-orange)</h3></a>

Какие из вариантов ответов предотвратят перезагрузку страницы?

- [x]
  ```html
  <form onsubmit="return false;" method="post">
    <input type="text" />
    <button type="submit">Отправить</button>
  </form>
  ```
- [x]
  ```javascript
  form.addEventListener('submit', (e) => {
	  e.preventDefault();
	})

  <form method="post">
    <input type="text" />
    <button type="submit">Отправить</button>
  </form>
  ```
- [ ]
  ```javascript
  form.addEventListener('submit', (e) => {
	  e.stopReload()
	})
  
  <form method="post">
    <input type="text" />
    <button type="submit">Отправить</button>
  </form>
  ```

<a name="6"><h3>6 ![](https://img.shields.io/badge/%D0%A1%D1%82%D0%B0%D1%82%D1%83%D1%81-%D0%9D%D0%B5%20%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BB%D0%B0%D1%81%D1%8C-orange)</h3></a>

Дан фрагмент кода:

```javascript
<script async src="script1.js"></script>
<script defer src="script2.js"></script>
```

script1 выполняется позже script2. Какой вариант кода позволит загрузить скрипты в правильном порядке?

1.
    ```javascript
      <script async src="script1.js"></script>
      <script async src="script2.js"></script>
    ```
  
2.
    ```javascript
      <script defer src="script1.js"></script>
      <script async src="script2.js"></script>
    ```
  
3. ✅
    ```javascript
      <script defer src="script1.js"></script>
      <script defer src="script2.js"></script>
    ```

<a name="7"><h3>7 ![](https://img.shields.io/badge/%D0%A1%D1%82%D0%B0%D1%82%D1%83%D1%81-%D0%9D%D0%B5%20%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BB%D0%B0%D1%81%D1%8C-orange)</h3></a>

Что то с вариантами порядка рендера страницы

----

<a name="10"><h3>10 ![](https://img.shields.io/badge/%D0%A1%D1%82%D0%B0%D1%82%D1%83%D1%81-%D0%9F%D1%80%D0%BE%D0%B9%D0%B4%D0%B5%D0%BD%D1%8B%20%D0%B2%D1%81%D0%B5%20%D1%82%D0%B5%D1%81%D1%82%D1%8B-brightgreen)</h3></a>

Дана функция которая получает результаты трёх лучших игроков:

```javascript
function getTop3(score) {
  return score.sort().reverse().slice(0, 3);
}

getTop3([1, 10, 5, 1, 12, 8])
```

Найдите ошибку и исправьте её.

**Решение:**

```javascript
function getTop3(score) {
  return score.sort(function(a, b) {
   return b - a;
  }).slice(0, 3);
}
```

<a name="11"><h3>11 ![](https://img.shields.io/badge/%D0%A1%D1%82%D0%B0%D1%82%D1%83%D1%81-%D0%9F%D1%80%D0%BE%D0%B9%D0%B4%D0%B5%D0%BD%D1%8B%20%D0%B2%D1%81%D0%B5%20%D1%82%D0%B5%D1%81%D1%82%D1%8B-brightgreen)</h3></a>

Дана функция:

```javascript
function replaceCurrencyNameWithSymbol(str, currencyName, currencySymbol) {
  return str.replace(currencyName, currencySymbol);
}

replaceCurrencyNameWithSymbol('Приход: 10 руб., сумма: 100 руб.', 'руб.', '₽')
```

Поймите что делает этот код и исправьте ошибку.

**Решение:**

```javascript
function replaceCurrencyNameWithSymbol(str, currencyName, currencySymbol) {
  return str.replaceAll(currencyName, currencySymbol);
}
```

<a name="12"><h3>12 ![](https://img.shields.io/badge/%D0%A1%D1%82%D0%B0%D1%82%D1%83%D1%81-%D0%9F%D1%80%D0%BE%D0%B9%D0%B4%D0%B5%D0%BD%D1%8B%20%D0%B2%D1%81%D0%B5%20%D1%82%D0%B5%D1%81%D1%82%D1%8B-brightgreen)</h3></a>

Дан фрагмент кода:

```javascript
arr.map(getNumber).filter(isNotNull)

function getNumber(item: string): number | null {
  return +item || null
}
```

Напишите типизированную функцию isNotNull.

**Решение:**

```javascript
function isNotNull(item: number | null) item is number {
  return typeof item === 'number';
}
```
   
<a name="13"><h3>13 ![](https://img.shields.io/badge/%D0%A1%D1%82%D0%B0%D1%82%D1%83%D1%81-%D0%9D%D0%B5%20%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BB%D0%B0%D1%81%D1%8C-orange)</h3></a>
   
Выберите, какие действия с объектом приведут к такому выводу в консоль:
   
```javascript
const object = { name: 'Fred', surname: 'Mercury' };
// ???
console.log({...object}); // -> {surname: Mercury}
```
   
- [ ] `Object.defineProperty(object, 'name', { enumerable: true })`
      
- [x] `Object.defineProperty(object, 'name', { enumerable: false })`
      
- [x] `delete object.name;`
      
- [ ] `object = {surname: 'Mercury'}`
   
<a name="14"><h3>14 ![](https://img.shields.io/badge/%D0%A1%D1%82%D0%B0%D1%82%D1%83%D1%81-%D0%9D%D0%B5%20%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BB%D0%B0%D1%81%D1%8C-orange)</h3></a>

Допишите код так, чтобы в консоль выводилось true:

```javascript
const object = {};
// TODO: здесь ваш код
console.log(object == '1');
```

**Решение:**

```javascript
Object.defineProperty(object, 'toString', {value: () => '1'})
```

<a name="15"><h3>15 ![](https://img.shields.io/badge/%D0%A1%D1%82%D0%B0%D1%82%D1%83%D1%81-%D0%9D%D0%B5%20%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BB%D0%B0%D1%81%D1%8C-orange)</h3></a>

Допишите код так, чтобы в консоль выводилось true:

```javascript
const object = Object.freeze({});
// TODO: здесь ваш код
console.log(object == '1');
```

**Решение:**

```javascript
a.__proto__.toString = () => '1'
```

<a name="16"><h3>16 ![](https://img.shields.io/badge/%D0%A1%D1%82%D0%B0%D1%82%D1%83%D1%81-%D0%9F%D1%80%D0%BE%D0%B9%D0%B4%D0%B5%D0%BD%D1%8B%20%D0%B2%D1%81%D0%B5%20%D1%82%D0%B5%D1%81%D1%82%D1%8B-brightgreen)</h3></a>

Реализуйте тип – неотрицательное число для работы в функции квадратного корня.

```javascript
function sqrt<N extends number>(n: NonNegativeNumber<N>): number {
  return Math.sqrt(n);
}
```

**Решение:**

```javascript
type NonNegativeNumber<N extends number> = number extends N ? N : `${N}` extends '-${string}' ? never : N;
```

<a name="17"><h3>17 ![](https://img.shields.io/badge/%D0%A1%D1%82%D0%B0%D1%82%D1%83%D1%81-%D0%9F%D1%80%D0%BE%D0%B9%D0%B4%D0%B5%D0%BD%D1%8B%20%D0%B2%D1%81%D0%B5%20%D1%82%D0%B5%D1%81%D1%82%D1%8B-brightgreen)</h3></a>

Напишите тип для массива, элементами которого могут быть строка или такой же массив (элементами которого могут быть строка или такой же массив и т.д.)

Например, тип должен позволять такое:

```javascript
const myRecursiveArray = ['test', [], ['test2']];
```

**Решение:**

```javascript
type ValueOrArray<T> = T | ValueOrArray<T>[];
type RecursiveArray = ValueOrArray<string>;
```

<a name="18"><h3>18 ![](https://img.shields.io/badge/%D0%A1%D1%82%D0%B0%D1%82%D1%83%D1%81-%D0%9D%D0%B5%20%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B0-red)</h3></a>

Перед вами реализация данных – множества, в которой элементы можно добавлять только один раз.
После удаления элемент нельзя добавить снова.

Подумайте, что здесь не так и исправьте ошибку.

```javascript
class OnceSet extends Set {
  added = new Set();
  
  add(el) {
    if (this.added.has(el)) {
      return this;
    }
    
    this.added.add(el);
    return super.add(el);
  }
}
```

<a name="19"><h3>19 ![](https://img.shields.io/badge/%D0%A1%D1%82%D0%B0%D1%82%D1%83%D1%81-%D0%9D%D0%B5%20%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BB%D0%B0%D1%81%D1%8C-orange)</h3></a>

Напишите функцию requestWithRetry, которая принимает функцию запроса и количество раз, которое этот запрос нужно повторять до успешного результата.

Retry должен вернуть промис с результатом или реджектом в случае, если все попытки провалились.

Пример использования:

```javascript
const results = await requestWithRetry(someFunction, 5);
```

**Решение:**

```javascript
/**
 * @param request () => Promise<T> функция запроса
 * @param attempts number сколько раз пытаемся сделать запрос
 * @return Promise<T> с результатом или реджектом
 */
async function requestWithRetry(request, attempts = 1) {
  const requestCount = 1;

  return new Promise(function(resolve, reject) { 
    while (requestCount <= attempts) {
      try {
        const result = request()
	resolve(result);
	break;
      } catch(err) {
	if (requestCount < attempts) {
	  requestCount++;
	} else {
	  reject(err);
	  break;
	}
      }
    }
  })
}
```

<a name="20"><h3>20 ![](https://img.shields.io/badge/%D0%A1%D1%82%D0%B0%D1%82%D1%83%D1%81-%D0%A0%D0%B5%D1%88%D0%B5%D0%BD%D0%B0%20%D1%87%D0%B0%D1%81%D1%82%D0%B8%D1%87%D0%BD%D0%BE-yellow)</h3></a>

Напишите функцию, которая принимает функцию запроса и максимальное время его ожидания. Возвращает промис с результатом запроса или реджектом в случае, если ответ не получен за назначенное время.

**Решение:**

```javascript
/**
 * @param request () => Promise<T>
 * @param timeout number время ожидания
 * @return Promise<T> с результатом или реджектом
 */
async function requestWithTimeout(request, timeout) {
  return new Promise(function(resolve, reject) {
    const timer = setTimeout(() => {
      reject()
    }, timeout);

    try {
      const result = request()
      resolve(result);
      clearTimeout(timer);
    } catch(err) {
      reject(err)
    }
  })
}
```


<a name="21"><h3>21 ![](https://img.shields.io/badge/%D0%A1%D1%82%D0%B0%D1%82%D1%83%D1%81-%D0%9D%D0%B5%20%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B0-red)</h3></a>

Реализуйте функцию excludePaths, принимающую объект и список путей, которые надо исключить и возвращающую новый объект без этих путей. Например:

```javascript
const alice = {
  name: 'Alice',
  age: 20,
  track: {
    title: 'Frontend',
    score: 100,
  }
}

const newObj = excludePaths(alice, ['age', 'track.score']);

console.log(newObj); // -> { name: 'Alice', 'track': {title: 'Frontend'} }
```

**Решение:**

```javascript
function excludePaths(obj, paths) {
  // реализуйте эту функцию
}
```

<a name="22"><h3>22 ![](https://img.shields.io/badge/%D0%A1%D1%82%D0%B0%D1%82%D1%83%D1%81-%D0%9D%D0%B5%20%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B0-red)</h3></a>

От коллег вам достался код, возвращающий N-ю страницу рейтинга участников.

Вам показалось, что код избыточный. Перепишите его более лаконично, не меняя функциональность:

```javascript
// page 1-based
function getParticipants(arr, track, size, page) {
  const arr2 = [];

  for (let i = 0; i < arr.length; i++) {
    if (arr[i].track === track) {
      arr2.push(arr[i]);
    }
  }

  for (let i = 0; i < arr2.lentgh; i++) {
    for (let j = i + 1; j < arr2.legth; j++) {
      if (arr2[i].name > arr2[j].name) {
        const temp = arr2[i];
        arr2[i] = arr2[j];
        arr2[j] = temp;
      }
    }
  }
  
  const arr3 = [];
  
  const first = size * (page - 1);

  for (let i = 0; i < arr2.length; i++) {
    if (first <= i && i < first + size) {
      arr3.push(arr2[i]);
    }
  }
  
  return arr3;
}
```

<a name="23"><h3>23 ![](https://img.shields.io/badge/%D0%A1%D1%82%D0%B0%D1%82%D1%83%D1%81-%D0%9D%D0%B5%20%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B0-red)</h3></a>

Напишите типизированную функцию getMax, которая принимает на вход массив элементов и функцию сравнения, а возвращает самый большой элемент массива согласно функции сравнения.

Если на вход передан пустой массив, то функция должна возвращать undefined.

**Решение:**

```javascript
function getMax(arr, comparator) {
  // реализуйте эту функцию и добавьте типизацию
}
```

<a name="24"><h3>24 ![](https://img.shields.io/badge/%D0%A1%D1%82%D0%B0%D1%82%D1%83%D1%81-%D0%9D%D0%B5%20%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B0-red)</h3></a>

Вам надо загрузить огромный файл на сервер. Напишите функцию, которая сделает это чанками в несколько потоков. Не меняйте интерфейсы, которые даны в задании.

```javascript
type Options = {
  maxChunks: number;
  chunkSize: number;
}

interface Source {
  readonly size: number;
  read(start: number, end: number): Blob;
}

type SendCb = (data: Blob, offset: number) => Promise<void>;

export async function upload(file: Source, send: SendCb, options: Options): Promise<unknown> {
}
```

**Решение:**

```javascript
type Options = {
  maxChunks: number;
  chunkSize: number;
}

interface Source {
  readonly size: number;
  read(start: number, end: number): Blob;
}

type SendCb = (data: Blob, offset: number) => Promise<void>;

export async function upload(file: Source, send: SendCb, options: Options): Promise<unknown> {
  ...
}
```

<a name="25"><h3>25 ![](https://img.shields.io/badge/%D0%A1%D1%82%D0%B0%D1%82%D1%83%D1%81-%D0%9D%D0%B5%20%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B0-red)</h3></a>

Напишите декоратор, который логирует переданные в метод аргументы, вернувшееся значение и время исполнения функции в заданном формате.

Пример использования:

```javascript
class SomeService {
  @Logger
  requestSomeData(id: number, provider: string): SomeData {
    // возвращает {name: 'Alice'}
    return loadData(id, provider);
  }
}

const service = new SomeService();
const result = service.requestSomeData(1, 'test provider');
```

В консоли появляется:

```
SomeService.requestSomeData: 0.033ms
  arguments: [1, "test-provider"]
  result: {"name": "Alice"}
```

**Решение:**

```javascript
// TODO: реализуйте декоратор
function Logger() {
  ...
}
```
