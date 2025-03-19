# LR4_Kolpakov_ISP41

# Soda Class Examples

Этот репозиторий содержит примеры использования класса `Soda` в Python. Класс `Soda` позволяет создавать объекты газировки с различными добавками.

## Пример 1: Базовое использование

python
class Soda:
    def init(self, additive=None):
        self.additive = additive


def show_my_drink(self):
    if self.additive:
        print(f"Газировка и {self.additive}")
    else:
        print("Обычная газировка")

drink1 = Soda()
drink2 = Soda('малина')
drink3 = Soda(5)  # Добавка может быть любого типа
drink1.show_my_drink()  # Вывод: Обычная газировка
drink2.show_my_drink()  # Вывод: Газировка и малина
drink3.show_my_drink()  # Вывод: Газировка и 5


В этом примере показано создание экземпляров класса `Soda` с различными добавками и без них. Метод `show_my_drink` выводит описание напитка.

## Пример 2: Переопределение метода `__str__`

python
class Soda:
    def init(self, additive=None):
        self.additive = additive


def __str__(self):
    if self.additive:
        return f"Газировка с {self.additive}"
    else:
        return "Обычная газировка"

def show_my_drink(self):  # Оставил этот метод для совместимости
    if self.additive:
        print(f"Газировка и {self.additive}")
    else:
        print("Обычная газировка")

drink1 = Soda()
drink2 = Soda('малина')
drink3 = Soda(5)
drink1.show_my_drink() # Вывод: Обычная газировка
drink2.show_my_drink() # Вывод: Газировка и малина
drink3.show_my_drink() # Вывод: Газировка и 5
print(drink1)  # Вывод: Обычная газировка
print(drink2)  # Вывод: Газировка с малина


В этом примере переопределен метод `__str__`, что позволяет получить строковое представление объекта `Soda` при использовании функции `print()`.  Обратите внимание, что метод `show_my_drink` теперь избыточен, т.к. функциональность уже есть в `__str__`.

## Пример 3: `__repr__`, `__del__` и `show_my_drink`

python
class Soda:
    def init(self, additive=None):
        self.additive = additive


def __str__(self):
    if self.additive:
        return f"Газировка с {self.additive}"
    else:
        return "Обычная газировка"

def __repr__(self):
    return f"Soda(additive='{self.additive}')"

def __del__(self):
    print("Объект Soda удален")

def show_my_drink(self): # Оставил этот метод для совместимости
    if self.additive:
        print(f"Газировка и {self.additive}")
    else:
        print("Обычная газировка")

drink1 = Soda()
drink2 = Soda('малина')
drink3 = Soda(5)
drink1.show_my_drink() # Вывод: Обычная газировка
drink2.show_my_drink() # Вывод: Газировка и малина
drink3.show_my_drink() # Вывод: Газировка и 5
print(drink1)  # Вывод: Обычная газировка
print(drink2)  # Вывод: Газировка с малина
print(repr(drink3)) # Вывод: Soda(additive='5')
del drink1         # Вывод: Объект Soda удален (может не сработать сразу)

В этом примере добавлены методы `__repr__` и `__del__`.

*   `__repr__` возвращает строковое представление объекта, которое можно использовать для его воссоздания.
*   `__del__` вызывается при удалении объекта сборщиком мусора (garbage collector).  Важно отметить, что вызов `del` не гарантирует немедленное удаление объекта, сборщик мусора может сработать позже.

## Замечания

*   В примерах 1 и 2, в классах `Soda` метод `__init__` принимает аргумент `additive` по умолчанию равный `None`. Это позволяет создавать объекты газировки как с добавками, так и без них.
*   Метод `show_my_drink` может быть удален в пользу переопределенного метода `__str__`.
