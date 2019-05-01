
# Классы в Java
ООП - Объектно ориентированное программирование. Мы имеем класс - описание объекта и сам объект, который мы создали с помощью нашего описания. К примеру: классом будет чертёж радио а объектом само радио
Вот пример создания класса:
```java
public class Radio {

}
```
А затем в классе ```Main``` создадим объект класса ```Radio```:
```java
public class Main {
	public static void main(String[] args) {
		Radio radio = new Radio();
	}
}
```
Разберём подробнее: Radio - название класса, radio название нашего объекта, = new Radio() - вызов конструктора и создание нового объекта с помощью слова ```new```.

Мы так же можем создать несколько объектов этого класса
Например:
```java
public class Main {
	public static void main(String[] args) {
		Radio notMyRadio = new Radio();
    		Radio myRadio = new Radio();
	}
}
```
Либо можем просто приписать уже существующий объект к нашей ссылке
Например:
```java
public class Main {
	public static void main(String[] args) {
		Radio notMyRadio = new Radio();
   		Radio myRadio = notMyRadio
	}
}
```
Как можно заметить, для myRadio мы не создаём нового радио а приписываем старое и если мы вызовем метод ```notMyRadio.equals(myRadio)``` то он вернёт нам ```true``` что значит, что это один и тот же объект.

## Атрибуты
В классе мы можем хранить данные, например для класса радио мы можем сохранить его название, количество кнопок, страну производителя и многое другое, что может пригодится нам в будущем.

Например для класса ```Person``` мы хотим сохранить имя человека, фамилию, и число, которое равно его годам. Вот как это будет выглядеть:
```java
public class Person {
	String name;
	String surName;
	int years;
}
```
Как мы видим, класс называется ```Person``` с большой буквы Затем внутри класса у нас есть ```String name```, ```String surName``` в которых мы храним имя и фамилию и затем ```int years``` для того, чтобы хранить года этого человека.

После описания класса, мы можем создать новый объект в классе ```Main``` :
```java
public static void main(String[] args) {
	Person maksym = new Person();		
}
```
Мы создали новый объект ```maksym``` класса ```Person``` 
Но поля в объекте ```maksym``` ещё пустые. Что если мы хотим записать в ```maksym``` имя, фамилию и количество лет?
Вот как мы можем это сделать:
```java
public class Main {
	public static void main(String[] args) {
		Person maksym = new Person();
		maksym.name = "Maksym";
		maksym.surName = "Pupkin";
		maksym.years = 43;
	}
}
```
Чтобы получить доступ к чему-либо внутри класа, мы используем ```.``` точку. ```maksym.name``` даст нам доступ к имени объекта
```maksym.surName``` к фамилии и т.д.

Затем мы можем вывестии эти данные на консоль таким способом:
```java
public class Main {
	public static void main(String[] args) {
		Person maksym = new Person();
		maksym.name = "Maksym";
		maksym.surName = "Pupkin";
		maksym.years = 43;
		
		System.out.println("Имя " + maksym.name + " фамилия " + maksym.surName + " кол-во лет " + maksym.years);
	}
}
```
