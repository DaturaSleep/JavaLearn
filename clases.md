
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
Как можно заметить, для myRadio мы не создаём нового радио а приписываем старое и если мы вызовем метод ```notMyRadio.equals(myRadio)``` то он вернёт нам ```true```
