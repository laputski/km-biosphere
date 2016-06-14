## ЛБ2: Основы
* Факториал - очевидно.
* getGrayCode - возвращает число, переведенное в код Грея в десятичной форме записи.
Чтобы увидеть обычное представление(0 или 1), нужно на результат подействовать
функцией toBinary - она вернет двоичное представление десятичного числа.
* decode - переводит число из кода Грея в десятичное.
Число, которое вводится - десятичное, в компьютере уже в двоичном виде, который(вид)
является кодом Грея для какого-то десятичного числа. Оно и возвращается. Чтобы лучше
понять, ввести какое-то десятичное число, посмотреть результат и сравнить с таблицей
соответствия(в главном классе с main).
* encode - переводит десятичное число в код Грея методом getGrayCode. Чтобы увидеть
обычное представление(0 или 1), нужно на результат подействовать функцией toBinary - она
вернет двоичное представление десятичного числа.
* В интерфейсе(в отдельном файле) прописываю его методы.
* Класс ChromosomeCode наследует интерфейс, в котором я создаю объект класса grayCode, а
потом после команды @override описываю методы интерфейса на основе методов класса
grayCode, примененные к созданному объекту.(задание 5а)
* В классе ChromosomeCode создаю класс GrayCode_inner, который наследует класс 
GrayCode. Создаю public объект данного класса obj2 и для него могу вызывать функции
базового класса.
Внутренние классы лучше использовать, когда два класса тесно и часто взаимодействуют
друг с другом. Это позволяет группировать классы, вязанные друг с другом.
* Аналогично создаю static GrayCode_nested(вложенный класс).
Этот класс логически связан с классом-владельцем, но может быть использован отдельно
от него.
* Анонимный класс удобно использовать, когда нужно одноразово переопределить методы или
создать собственные методы объекта.
* Для проверки правильности работы методов в главном классе созданы эти же методы и вызваны.
Все проверки на одинаковых числах.
* Проверка public класса:
в классе ChromosomeCode создаю public объект класса GrayCode, переписываю методы
интерфейса, используя класс GrayCode.
В main создаю объект класса ChromosomeCode и для него вызываю методы.
* Проверка inner класса:
в классе ChromosomeCode создаю public объект класса GrayCode_inner, а в main
создаю объект класса ChromosomeCode, получаю доступ к его внутреннему объекту и для
него вызываю нужные методы.
* Проверка nested класса:
в main создаю объект класса ChromosomeCode.GrayCode_nested и к нему применяю нужные
методы.
* Проверка анонимного класса:
в main при создании объекта класса ChromosomeCode переписываю один из методов, при 
вызове убеждаюсь, что метод переписан. 
*  == - сравнение ссылок
ex1,ex2 - объекты одного класса
ex1.equals(ex2) - сравнение значений.
2-й объект ссылается на 1-й и значения у них одинаковые => true в обоих случаях
16.Все классы протестированы в main


## ЛБ3: Коллекции
* Иетоды классов для работы с колекциями знают, к чему применяться благодаря доп
аргументу функции(номер коллекции) и switch внутри их:
числам 1-8 соответствуют свои коллекции.
/*
1-ArrayList
2-LinkedList
3-HashMap
4-LinkedHashMap
5-TreeMap
6-HashSet
7-LinkedHashSet
8-TreeSet
*/
* Генерирую случайные записи, привожу их к типу данных String, заполняю ими коллекции
с помощью функций add или put.
class DataGenerator -> void add
* Метод search(class DataGenerator) ищет в колекциях элементы, которых там нет
(чтобы проверить все элементы; у меня строку "hello").
* deleteNumberOFElements(class DataGenerator) удаляет нужное количество элементов
выбранной коллекции. У меня удаляются все. При необходимости в while просто поменять
условие и добавить переменную-счетчик.
* cleanCollection(class DataGenerator) удаляет все элементы коллекции при помощи
встроенной функции. Этот метод я вызываю после того, как отработали тесты
производительности для выбранного количества записей(в том числе и удаление), 
чтобы они точно были пустыми при их следующем использовании, хотя этого можно
и не делать.
* В class PerformanceComparator создаю массив из номеров коллекций(1-8), объект
класса DataGenerator и к нему применяю все методы класса DataGenerator.
* smallPerformanceTest - тесты производительности для одного количетсва записей.
* fullTestPerformance - тесты производительности для всех количеств записей
(на входе массив из чисел, которые обозначают количество записей в тесте).
* В main на всякий случай делаю приведение типов для количества записей, остальное
все понятно.
* ArrayList vs LinkedList
На маленьких объемах данных ArrayList намного медленне только на вставке.
На средних примерно в два раза медленне при вставке. Примерно паритет при поиске.
Удаление - ОЧЕНЬ медленно. 
На больших данных ArrayList оказывается даже быстрее при вставке и поиске, но при
удалении скорость ОЧЕНЬ ОЧЕНЬ ОЧЕНЬ малеьнкая. 
* HashMap vs TreeMap
На маленьких данных TreeMap работает примерно от 1,5 до 3 раз быстрее.
На средних TreeMap быстрее во вставке, но чуть медленнее при поиске и удалении.
На больших данных TreeMap медленнее при вставке, но быстрее при поиске и удалении.
Примечание: на разных компьютерах получились разные результаты(относительные), причем они
не слабо отличаются, например HashMap чуть ли не везде опережает TreeMap от 20 до 300%.
Copyright@Воробей Влад:)