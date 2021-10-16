## <a name="variable"></a>Как объявить переменную в TypeScript?

Вы можете создавать переменные тремя способами: `var`, `let` и `const`.

`var` - это старый стиль объявления переменных.

`let` - это способ объявления переменных в TypeScript по умолчанию. По сравнению с `var` `let` уменьшает количество ошибок времени компиляции и повышает читаемость кода.

```typescript
let num: number = 1;
```

`const` создает постоянную переменную, значение которой не может измениться. Он использует те же правила области видимости, что и let, и помогает снизить общую сложность программы.

```typescript
const num: number = 100;
```

## <a name="constructor"></a>Как вызвать конструктор базового класса из дочернего класса в TypeScript?

Вы можете использовать функцию `super()` для вызова конструктора базового класса.

```typescript
class Animal {
	name: string;
	constructor(theName: string) {
		this.name = theName;
	}
	move(distanceInMeters: number = 0) {
		console.log(`${this.name} moved ${distanceInMeters}m.`);
	}
}

class Snake extends Animal {
	constructor(name: string) {
		super(name);
	}
	move(distanceInMeters = 5) {
		console.log("Slithering...");
		super.move(distanceInMeters);
	}
}
```

## <a name="mixins"></a>Объясните как использовать миксины в TypeScript.

TypeScript, как и многие объектно-ориентированные языки, не позволяет использовать напрямую множественное наследование. Из-за этого, не смотря на то, что можно реализовать множество интерфейсов в классе, унаследовать его можно только от одного класса.
Примесь – объект, содержащий методы и свойства для реализации конкретного функционала.
Функциональность миксинов (mixins) частично позволяет унаследовать свойства и методы сразу двух и более классов, тем самым избавившись от дублирования в коде.

## <a name="null-undefined"></a>Как проверить на null или undefined?

Рекомендуется проверять `== null` как на `undefined`, так и `null`.
Также Nullish Coalescing (оператор `??`) помогает проверить, является ли переменная `null` или `undefined`.
С оператором `??` вместо длинной проверки

```typescript
message = undefined;
getMessage() {
	if (this.message !== null && this.message !== undefined) {
		return "default message";
	}
	return this.message;
}
```

можно написать так:

```typescript
message = undefined;
getMessage() {
	return this.message ?? 'Default message';

}
```

## <a name="getter-setter"></a>Что такое getters/setters? Как их использовать?

Геттеры и сеттеры - это особые типы методов, которые помогают делегировать различные уровни доступа к частным переменным в зависимости от потребностей программы.

Геттеры позволяют ссылаться на значение, но не могут его редактировать. Сеттеры позволяют изменять значение переменной, но не видеть ее текущее значение. Это важно для достижения инкапсуляции.

Например, новый работодатель может получить количество сотрудников в компании, но не имеет разрешения устанавливать количество сотрудников.

```typescript
const fullNameMaxLength = 10;

class Employee {
	private _fullName: string = "";

	get fullName(): string {
		return this._fullName;
	}

	set fullName(newName: string) {
		if (newName && newName.length > fullNameMaxLength) {
			throw new Error("fullName has a max length of " + fullNameMaxLength);
		}

		this._fullName = newName;
	}
}

let employee = new Employee();
employee.fullName = "Bob Smith";

if (employee.fullName) {
	console.log(employee.fullName);
}
```

## <a name="accessible-outside"></a>Как сделать так, чтобы классы, определенные в модуле, были доступны вне модуля?

Вы можете использовать ключевое слово `export`, чтобы классы, определенные вне модуля.

```typescript
module Admin {
	// use the export keyword in TypeScript to access the class outside
	export class Employee {
		constructor(name: string, email: string) {}
	}
	let alex = new Employee("alex", "alex@gmail.com");
}

// The Admin variable will allow you to access the Employee class outside the module with the help of the export keyword in TypeScript
let nick = new Admin.Employee("nick", "nick@yahoo.com");
```

## <a name="convert"></a>Как преобразовать строку в число с помощью TypeScript?

Подобно JavaScript, вы можете использовать функции `parseInt` или `parseFloat` для преобразования строки в целое число или число с плавающей запятой соответственно. Вы также можете использовать унарный оператор `+` для преобразования строки в наиболее подходящий числовой тип, «3» становится целым числом 3, а «3.14» становится вещественным числом 3.14.

## <a name="map"></a>Что такое файл .map? Зачем и как его можно использовать?

Файл map - это исходная карта, которая показывает, как исходный код TypeScript был интерпретирован в пригодный для использования код JavaScript. Они помогают упростить отладку, поскольку вы можете отловить любое странное поведение компилятора.

Инструменты отладки также могут использовать эти файлы, чтобы вы могли редактировать базовый TypeScript, а не создаваемый файл JavaScript.

## <a name="classes"></a>Что такое классы в TypeScript?

Классы представляют собой общие поведения и атрибуты группы связанных объектов.

Например, нашим классом может быть `Student`, у каждого из которых есть метод `attendClass`. С другой стороны, `John` является отдельным экземпляром типа `Student` и может иметь дополнительные уникальные поведения, такие как `attendExtracurricular`.

Вы объявляете классы с помощью ключевого слова `class`:

```typescript
class Student {
	studCode: number;
	studName: string;
	constructor(code: number, name: string) {
		this.studName = name;
		this.studCode = code;
	}
}
```
