Для случая наследования класов:

    public class Child extends Parent

поля объекта инициализируются в следующем порядке:

1.     Статические поля класса Parent;
1.     Статический блок инициализации класса Parent;
1.     Статические поля класса Сhild;
1.     Статический блок инициализации класса Child;
1.     Нестатические поля  класса Parent;
1.     Нестатический блок инициализации класса Parent;
1.     Конструктор класса Parent;
1.     Нестатические поля  класса Сhild;
1.     Нестатический блок инициализации класса Сhild;
1.     Конструктор класса Сhild.
