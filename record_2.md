# Конспект №2: static, string.
## Содержание
1. Статические переменные (static) C++
2. Строковый тип (string) в C++

## Статические переменные в C++
Ключевое слово **static** ограничивает действие переменной границами программы, если использовано к ней вне блока, и снимает ограничения её действия границами блока, если использовано внутри блока:

    void valuePrint() {
      int value = 0;            // Без ключевого слова static
      ++value;                  // Увеличивается переменная внутри блока
      std::cout << value;       // Выводится одна и та же
    }
 
    int main() {
      valuePrint();            // Вывод - 1
      valuePrint();            // Вывод - 1
      valuedPrint();           // Вывод - 1
    }
    
Использование **static** позволяет правильно организовать идентификаторы:

    void valuePrint() {
      static int s_value = 0;     // C ключевым словом static
      ++s_value;                  // Увеличивается переменная внутри блока
      std::cout << s_value;       // Выводится одна и та же
    }
 
    int main() {
      valuePrint();            // Вывод - 1
      valuePrint();            // Вывод - 2
      valuedPrint();           // Вывод - 3
    }

Несмотря на то, что статические переменные сохраняют своё значение
- [Для чего нужны статические переменные?](https://ravesli.com/urok-51-staticheskie-peremennye/)

## Строковый тип в C++
Строковый тип поддерживается библиотекой **<string>** и пространством имён **std**.

    #include <string>             // Подлючение библиотеки
    std::string name("Misha");    // Присвоение при инициализации
    name = "Misha";               // Присвоение при исполнении
    
Использование **std::cin** не позволяет использовать пробелы в строках. Для этого существует встроенное в библиотеку ключевое слово **std::getline**:

    std::cout << "Введите своё ФИО: ";   // Ввод ФИО в консоль через cin
    std::string name;                    // Создание строки
    std::getline(std::cin, name);        // Изъятие введённого из cin в getline
    
Строки реализуют следующие методы:
1. name.length() - возвращает длину строки беззнаковым типом
2. name.resize(length) - увеличивает или уменьшает длину строки
3. name.clear() - очищает строку
4. name.empty() - возвращает true, если строка пуста, иначе false
5. name.append(number, char) - добавляет в конец строки символы
6. name.erase(pos, cout) - удаляет часть строки
7. name.insert(index, number, char) - вставляет строку в середину строки
8. name.find(string, pos) - ищет вхождение строки в строке 

- [Как использовать строки в C++?](https://ravesli.com/urok-57-vvedenie-v-std-string/)
