# IT's Tinkoff Cup 2023 Frontend 2023

## 1
Дано SVG-изображение размером 500 х 200. Требуется, чтобы в приложении отображалось изображение размером 60 х 25. Выберите правильный набор параметров SVG для масштабирования.

1. width="60" height="25" viewBox="0 0 500 200"
2. width="60" height="25" viewBox="500 0 200 0"
3. width="60" height="25" viewBox="500 200"
4. width="500" height="200" viewBox="60 25 0 0"
5. width="500" height="200" viewBox="60 0 25 0"
6. width="500" height="200" viewBox="60 25"

## 2

У элемента заданы width и height, но если принять padding, то ширина и высота увеличиваются. Какое свойство помогает избежать этого?

1. box-sizing: content-box;
2. box-sizing: border-box;
3. box-sizing: initial;

## 3

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

1. Добавить .z2 { position: static }, .z1 { position: static }
2. Добавить .z2 { position: relative }, .z1 { position: static }
3. Добавить .z2 { position: relative }, .z1 { position: relative }
4. Добавить .z2 { position: absolute }, .z1 { position: relative }


## 4

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
  
3.
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
    
## 5

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

----

## 10

Дана функция которая получает результаты трёх лучших игроков:

```javascript
function getTop3(score) {
  return score.sort().reverse().slice(0, 3);
}

getTop3([1, 10, 5, 1, 12, 8])
```

Найдите ошибку и исправьте её.

<details>
  <summary>Решение</summary>
  <code>

    function getTop3(score) {
      return score.sort(function(a, b) {
        return b - a;
      }).slice(0, 3);
    }
  </code>
</details>

## 11

Дана функция:

```javascript
function replaceCurrencyNameWithSymbol(str, currencyName, currencySymbol) {
  return str.replace(currencyName, currencySymbol);
}

replaceCurrencyNameWithSymbol('Приход: 10 руб., сумма: 100 руб.', 'руб.', '₽')
```

Поймите что делает этот код и исправьте ошибку.

<details>
  <summary>Решение</summary>
  <code>

    function replaceCurrencyNameWithSymbol(str, currencyName, currencySymbol) {
      return str.replaceAll(currencyName, currencySymbol);
    }
  </code>
</details>

----
   
## 13
   
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
   
## 14

Допишите код так, чтобы в консоль выводилось true:

```javascript
const object = {};
// TODO: здесь ваш код
console.log(object == '1');
```

<details>
  <summary>Решение</summary>
  <code>Object.defineProperty(object, 'toString', {value: () => '1'})</code>
</details>

## 15

Допишите код так, чтобы в консоль выводилось true:

```javascript
const object = Object.freeze({});
// TODO: здесь ваш код
console.log(object == '1');
```

<details>
  <summary>Решение</summary>
  <code>a.__proto__.toString = () => '1'</code>
</details>

## 16

Реализуйте тип – неотрицательное число для работы в функции квадратного корня.

```javascript
function sqrt<N extends number>(n: NonNegativeNumber<N>): number {
  return Math.sqrt(n);
}
```

<details>
  <summary>Решение</summary>
  <code>type NonNegativeNumber<N extends number> = number extends N ? N : `${N}` extends '-${string}' ? never : N;</code>
</details>

## 17

Напишите тип для массива, элементами которого могут быть строка или такой же массив (элементами которого могут быть строка или такой же массив и т.д.)

Например, тип должен позволять такое:

```javascript
const myRecursiveArray = ['test', [], ['test2']];
```

<details>
  <summary>Решение</summary>
  <code>

    type ValueOrArray<T> = T | ValueOrArray<T>[];
    type RecursiveArray = ValueOrArray<string>;
  </code>
</details>

## 18

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

## 19

Напишите функцию requestWithRetry, которая принимает функцию запроса и количество раз, которое этот запрос нужно повторять до успешного результата.

Retry должен вернуть промис с результатом или реджектом в случае, если все попытки провалились.

Пример использования:

```javascript
const results = await requestWithRetry(someFunction, 5);
```

<details>
  <summary>Решение</summary>
  <code>

    /**
     * @param request () => Promise<T> функция запроса
     * @param attempts number сколько раз пытаемся сделать запрос
     * @return Promise<T> с результатом или реджектом
     */
    async function requestWithRetry(request, attempts = 1) {
      // реализуйте эту функцию
    }
  </code>
</details>

## 20

Напишите функцию, которая принимает функцию запроса и максимальное время его ожидания. Возвращает промис с результатом запроса или реджектом в случае, если ответ не получен за назначенное время.

<details>
  <summary>Решение</summary>
  <code>

    /**
     * @param request () => Promise<T>
     * @param timeout number время ожидания
     * @return Promise<T> с результатом или реджектом
     */
    async function requestWithTimeout(request, timeout) {
      // реализуйте эту функцию
    }
  </code>
</details>


## 21

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

<details>
  <summary>Решение</summary>
  <code>

    function excludePaths(obj, paths) {
      // реализуйте эту функцию
    }
  </code>
</details>

## 22

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

## 23

Напишите типизированную функцию getMax, которая принимает на вход массив элементов и функцию сравнения, а возвращает самый большой элемент массива согласно функции сравнения.

Если на вход передан пустой массив, то функция должна возвращать undefined.

<details>
  <summary>Решение</summary>
  <code>

    function getMax(arr, comparator) {
      // реализуйте эту функцию и добавьте типизацию
    }
  </code>
</details>


## 24

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

<details>
  <summary>Решение</summary>
  <code>

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
  </code>
</details>

## 25

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

<details>
  <summary>Решение</summary>
  <code>

    // TODO: реализуйте декоратор
    function Logger() {
    }
  </code>
</details>
