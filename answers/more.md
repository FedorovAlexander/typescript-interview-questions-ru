## <a name="default-modifier"></a>Назовите модификатор доступа по умолчанию?

По умолчанию все члены класса в TypeScript являются public (общедоступными). Доступ к ним можно получить где угодно без каких-либо ограничений.

## <a name="declare"></a>Когда нужно использовать ключевое слово declare?

Ключевое слово declare используется для внешних объявлений, в которых вы хотите определить переменную, которая, возможно, не была получена из файла TypeScript.

## <a name="generics"></a>Что такое дженерики в TypeScript?

Generics - это инструмент, который позволяет создавать компоненты, которые можно переиспользовать. Он создает компонент, который может работать с различными типами данных. Это позволяет пользователям использовать свои собственные типы. Generics гарантируют, что программа масштабируемой в долгосрочной перспективе.

```typescript
function identity<T>(arg: T): T {
	return arg;
}
let output1 = identity<string>("myString");
let output2 = identity<number>(100);
```

## <a name="enum"></a>Как и когда нужно использовать enum?

В TypeScript `enum` представляют собой структуры данных постоянной длины, которые содержат набор констант. `Enum` полезны при присвоении свойств или значений, которые могут быть только определенным количеством возможных значений. Одним из распространенных примеров является значение масти одной карты в колоде игральных карт. Есть только 4 масти и не существует других возможных значений, и эти значения вряд ли изменятся. По этой причине `enum` было бы эффективным и ясным способом описания возможных мастей карты.

## <a name="namespaces"></a>Что такое пространство имен и как его использовать?

Пространство имен используется для логической группировки функций. Пространство имен может включать интерфейсы, классы, функции и переменные для поддержки одной или группы связанных функций.

Пространство имен может быть создано с помощью ключевого слова `namespace`, за которым следует имя пространства имен. Все интерфейсы, классы и т. Д. Можно определить в фигурных скобках `{}`.

## <a name="optional"></a>Как реализовать необязательные параметры?

- Используйте синтаксис параметра `?: type`, чтобы сделать параметр необязательным.
- Используйте выражение `typeof (параметр)! == 'undefined'`, чтобы проверить, был ли параметр инициализирован.

```typescript
function multiply(a: number, b?: number, c: number): number {
	if (typeof c !== "undefined") {
		return a * b * c;
	}
	return a * b;
}
```

## <a name="is-functional"></a>TypeScript функциональный язык программирования?

TypeScript поддерживает некоторые методы функционального программирования - в основном потому, что он имеет те же функции высшего порядка и замыкания, что и JavaScript.

## <a name="reusable"></a>Как с помощью TypeScript сделать переиспользуемые компоненты?

Generics - это инструмент, который позволяет создавать компоненты, которые можно переиспользовать. Он создает компонент, который может работать с различными типами данных. Это позволяет пользователям использовать свои собственные типы. Generics гарантируют, что программа масштабируемой в долгосрочной перспективе.

```typescript
function identity<T>(arg: T): T {
	return arg;
}
let output1 = identity<string>("myString");
let output2 = identity<number>(100);
```

## <a name="tuple"></a>В чем разница между tuple и массивом в TypeScript?

Обычно `tuple` представляет собой фиксированного размера массив, состоящий из элементов известного типа. Порядок элементов должен соблюдаться.

```typescript
const primaryColors: [string, string, string] = [
	"#ff0000",
	"#00ff00",
	"#0000ff",
];
console.log(primaryColors);
```

## <a name="internal"></a>В чем разница между внутренними и внешними модулями TypeScript?

### Внешний модуль

Например. В файле main.d.ts:

```typescript
import log = module("log");
log.message("hello");
```

Этот ссылается на внешний модуль log, который определен в файле log.ts.

```typescript
export function message(s: string) {
	console.log(s);
}
```

### Внутренний модуль

В этом файле есть два внутренних модуля X.Y.Z.

```typescript
module A.B.C {
	import XYZ = X.Y.Z;
	export function ping(x: number) {
		if (x > 0) {
			XYZ.pong(x – 1)
			};
	}
}
module X.Y.Z {
	import ABC = A.B.C;
	export function pong(x: number) {
		if (x > 0) {
			ABC.ping(x – 1)
			};
	}
}
```

## <a name="collections"></a>Какие коллекции поддерживает TypeScript?

### Массивы

```typescript
let num: number[] = [1, 2, 3];
const numToo: Array<number> = [1, 2, 3];
```

### Tuples

```typescript
const life: [string, number] = ["everything", 42];
```

### Объекты

```typescript
const planet: { name: string; position: number } = {
	name: "earth",
	position: 3,
};
```

### Map

```typescript
const planet = new Map<string, string>();
planet.set("name", "earth");
planet.set("position", "1");

console.log(planet);
// Map { 'name' => 'earth', 'position' => '1' }
```

### Set

Набор - это упорядоченный список значений без дубликатов.

```typescript
const planet = new Set<string>();
planet.add("earth");

console.log(planet);
// Set { 'earth' }
```

### WeakMap и WeakSet

WeakMap

```typescript
const planet = new WeakMap<{ bodyType: string }, string>();
planet.set({ bodyType: "planet" }, "earth");
```

WeakSet

```typescript
const planet = new WeakSet<{ name: string }>();
planet.add({ name: "earth" });
```

## <a name="record"></a>Для чего используется тип Record?

## <a name="tech-stack"></a>В чем преимущества TypeScript?

## <a name="abstract"></a>TypeScript поддерживает абстрактные классы?
