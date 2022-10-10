```
public class JvmComprehension {

    public static void main(String[] args) {
        int i = 1;
```
// 1 - примитив идет в stack-пам€ть.
```
Object o = new Object();
```
// 2 - загрузка класса Object (Bootstrap Classloader). 
—сылка на o - в stack-пам€ть, а сам объект o - в heap.

```
Integer ii = 2;
```
// 3 - загрузка класса Integer (Bootstrap Classloader).
—сылка на ii - в stack-пам€ть, а сам объект ii - в heap.

```
 printAll(o, i, ii);
```

// 4 - инициализаци€ статического метода printAll.
сигнатура метода в stack'е, ссылки на o и ii тоже (i хранитс€ в stack'е как примитив).

```
System.out.println("finished");
```
// 7 - сигнатура метода и ссылка на строку - в stack'e, сама строка - в куче.

```
private static void printAll(Object o, int i, Integer ii) {
        Integer uselessVar = 700;
```
// 5 - —сылка на uselessVar - в stack-пам€ть, а сам объект -  в кучу.
```
System.out.println(o.toString() + i + ii);
```
// 6 - o.toString, ссылка на строку - в Stack, строка - в куче. ѕеременна€ i - из stack, ii - по ссылке из stack.
”даление uselessVar как объекта без св€зей.