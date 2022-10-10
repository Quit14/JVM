```
public class JvmComprehension {

    public static void main(String[] args) {
        int i = 1;
```
// 1 - �������� ���� � stack-������.
```
Object o = new Object();
```
// 2 - �������� ������ Object (Bootstrap Classloader). 
������ �� o - � stack-������, � ��� ������ o - � heap.

```
Integer ii = 2;
```
// 3 - �������� ������ Integer (Bootstrap Classloader).
������ �� ii - � stack-������, � ��� ������ ii - � heap.

```
 printAll(o, i, ii);
```

// 4 - ������������� ������������ ������ printAll.
��������� ������ � stack'�, ������ �� o � ii ���� (i �������� � stack'� ��� ��������).

```
System.out.println("finished");
```
// 7 - ��������� ������ � ������ �� ������ - � stack'e, ���� ������ - � ����.

```
private static void printAll(Object o, int i, Integer ii) {
        Integer uselessVar = 700;
```
// 5 - ������ �� uselessVar - � stack-������, � ��� ������ -  � ����.
```
System.out.println(o.toString() + i + ii);
```
// 6 - o.toString, ������ �� ������ - � Stack, ������ - � ����. ���������� i - �� stack, ii - �� ������ �� stack.
�������� uselessVar ��� ������� ��� ������.