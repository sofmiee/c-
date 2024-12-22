Вариант 6
1. Создайте базовый класс Building для представления здания. У класса
должны быть:
 Защищенные данные для хранения названия здания и количества
этажей.
 Конструктор для инициализации названия и количества этажей.
 Виртуальная функция virtual void display() const, которая выводит
информацию о здании.
2. Отнаследуйте от базового класса Building два класса:
ResidentialBuilding и OfficeBuilding.
 ResidentialBuilding должен иметь количество квартир и
переопределенную функцию display(), которая выводит информацию о
жилом доме.
 OfficeBuilding должен иметь количество офисов и переопределенную
функцию display(), которая выводит информацию о здании офисного
типа.
3. Создайте STL контейнер (например, std::list) для хранения указателей
на объекты классов Building. Заполните контейнер несколькими
объектами ResidentialBuilding и OfficeBuilding.
4. Используя итераторы STL, выведите информацию о каждом здании в
контейнере.
5. Напишите функцию, которая принимает указатель на базовый класс
Building и изменяет его характеристики. Функция должна работать с
любыми производными классами.
Примечание
 Помните об использовании деструкторов и освобождении памяти, если
это необходимо.
 Оценивайте правильность реализации ООП концепций (наследование,
полиморфизм) и корректность использования STL.
 Все данные задаются на этапе разработки, без потока ввода.
