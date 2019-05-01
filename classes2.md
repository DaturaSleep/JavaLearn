# Классы в Java

## Getter's & Setter's

### Setter
До этого момента мы обращались к атрибутам наших классов через ```.``` например: ```vova.name```, ```radio.size```. Такой подход является не совсемм правильным ведь мы не осуществляем никакого контроля над данными которые мы передаём. К примеру, нам ничто не мешает передать в переменную класса ```radio.size``` значение меньше нуля ```radio.size = -20```. По логике вещей мы не должны допускать этого. Для контроля над данными которые мы передаём в класс мы можем использовать конструкцию которая называется ```setter``` и ограничить доступ к атрибуту через модификатор доступа ```private```. 

Пример:
```java
public class SampleClass {
	private int size;
	
	public void setSize(int size) {
		if(size < 0 ) {
			System.out.println("Size can't be less than 0");
		}else {
			this.size = size;
		}
	}
}
```
Сеттер является обычным методом который не возвращает значение и в который мы передаём само значение. Называть сетеры принято в соответствии с именем переменной. К примеру если у нас переменная ```size``` то сеттер для этого атрибута мы назовём ```setSize```, для переменной ```mySecondName``` - ```setMySecondName```.
# Getter
Getter в свою очередь отвечает за возвращение данных. И он тоже осуществляет определённый контроль. Например если у нас ```radio.name``` имеет значение ```null``` то мы хотим, чтобы при обращении к этому атрибуту нам кидало какой-то ```exception```.

Пример:
```java
public class SampleClass {
	private int size;
	private String name;

	public String getName() {
		if (this.name == null) {
			throw new NullPointerException("Sample class yet has no name");
		} else {
			return this.name;
		}
	}
}
```

## Наследование классов
Наследование это одно из ключевых понятий ООП. При помощи наследования мы можем создать класс, который будет родительским классом и еще дополнительные классы, которые будут все унаследовать от главного класса.

Например создадим класс ```Person``` 
```java
public class Person {
	String name;
	String surname;
	int years;
}
```
И унаследуем от него класс ```Worker```  с помощью ключевого слова ```extends```.
```java
public class Worker extends Person{
	int salary;
}
```
А затем в класе ```Main``` создадим объект класса ```Worker``` и припишем ему значения ```name, surname, years, salary```.
```java
public class Main {
	public static void main(String args) {
		Worker w = new Worker();
		w.name = "Sanya";
		w.surname = "Vopkov";
		w.years = 35;
		w.salary = 1000;
	}
}
```
Как видно из кода выше, мы создали объект класса ```Worker``` который имеет доступ ко всем атрибутам как своего класса так и класса ```Person```.
