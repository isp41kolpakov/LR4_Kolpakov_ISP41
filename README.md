# Лабораторная работа №4. Классы

## Уровень 1:

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

## Уровень 2:

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

## Уровень 3:

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
