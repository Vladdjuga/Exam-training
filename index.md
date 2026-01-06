# Підготовка до екзамену / Przygotowanie do egzaminu

Цей документ містить питання до екзамену та пояснення до них двома мовами: українською та польською.
Niniejszy dokument zawiera pytania egzaminacyjne wraz z wyjaśnieniami w dwóch językach: ukraińskim i polskim.

## План / Spis treści

### Питання по керунку / Pytania kierunkowe

- [Питання 1: Co to jest polimorfizm dynamiczny. Podaj przykład i omów w jaki sposób w języku C++ ten rodzaj polimorfizmu jest realizowany.](#питання-1)
- [Питання 2: Jakie można wyróżnić modele procesu tworzenia oprogramowania. Scharakteryzuj niektóre z nich.](#питання-2)
- [Питання 3: Jakie są najprostsze algorytmy generacji liczb losowych z zadanym rozkładem prawdopodobieństwa?](#питання-3)
- [Питання 4: Na wybranych przykładach scharakteryzuj podstawowe typy, struktury i organizacje danych.](#питання-4)
- [Питання 5: Opisz cechy i składowe języka SQL, podaj jego wady i zalety.](#питання-5)
- [Питання 6: Omów pojęcie semaforów i przedstaw przykłady ich zastosowania.](#питання-6)
- [Питання 7: Omów przetwarzanie potokowe we współczesnych systemach komputerowych.](#питання-7)
- [Питання 8: Omów/Opisz różnice pomiędzy aproksymacją i interpolacją w kontekście wizualizacji danych.](#питання-8)
- [Питання 9: Proszę omówić budowę i uczenie sztucznej sieci neuronowej wielowarstwowej.](#питання-9)
- [Питання 10: Proszę omówić model referencyjny sieci komputerowej OSI/ISO.](#питання-10)
- [Питання 11: Proszę omówić translację adresów NAT oraz portów PAT w sieciach TCP/IP.](#питання-11)
- [Питання 12: Przedstaw sposób definicji typu strukturalnego w języku C++ oraz sposób definicji i korzystania ze zmiennej strukturalnej.](#питання-12)
- [Питання 13: Scharakteryzuj maszynę Turinga, omów jej złożoność oraz podaj różnice i podobieństwa pomiędzy deterministycznym a niedeterministycznym jej wariantem.](#питання-13)
- [Питання 14: Scharakteryzuj diagram klas notacji UML.](#питання-14)
- [Питання 15: Wymień i omów struktury systemów operacyjnych.](#питання-15)
- [Питання 16: Opisz różnicę pomiędzy algorytmami zachłannymi i dynamicznymi.](#питання-16)

### Питання по спеціальності / Pytania zakresowe

- [Питання 1](#питання-1-pytanie-1)
- [Питання 2](#питання-2-pytanie-2)
- [Питання 3](#питання-3-pytanie-3)
- [Питання 4](#питання-4-pytanie-4)
- [Питання 5](#питання-5-pytanie-5)
- [Питання 6](#питання-6-pytanie-6)
- [Питання 7](#питання-7-pytanie-7)
- [Питання 8](#питання-8-pytanie-8)
- [Питання 9](#питання-9-pytanie-9)
- [Питання 10](#питання-10-pytanie-10)
- [Питання 11](#питання-11-pytanie-11)
- [Питання 12](#питання-12-pytanie-12)
- [Питання 13](#питання-13-pytanie-13)
- [Питання 14](#питання-14-pytanie-14)
- [Питання 15](#питання-15-pytanie-15)
- [Питання 16](#питання-16-pytanie-16)
- [Питання 17](#питання-17-pytanie-17)
- [Питання 18](#питання-18-pytanie-18)
- [Питання 19](#питання-19-pytanie-19)
- [Питання 20](#питання-20-pytanie-20)
- [Питання 21](#питання-21-pytanie-21)
- [Питання 22](#питання-22-pytanie-22)
- [Питання 23](#питання-23-pytanie-23)
- [Питання 24](#питання-24-pytanie-24)
- [Питання 25](#питання-25-pytanie-25)
- [Питання 26](#питання-26-pytanie-26)
- [Питання 27](#питання-27-pytanie-27)
- [Питання 28](#питання-28-pytanie-28)
- [Питання 29](#питання-29-pytanie-29)
- [Питання 30](#питання-30-pytanie-30)
- [Питання 31](#питання-31-pytanie-31)
- [Питання 32](#питання-32-pytanie-32)
- [Питання 33](#питання-33-pytanie-33)

---

# Питання по керунку / Pytania kierunkowe

## Питання 1

**UA:** Що таке динамічний поліморфізм? Наведіть приклад і обговоріть, як цей вид поліморфізму реалізований у мові C++.

**PL:** Co to jest polimorfizm dynamiczny. Podaj przykład i omów w jaki sposób w języku C++ ten rodzaj polimorfizmu jest realizowany.

### Пояснення / Wyjaśnienie

**UA:**
Для того щоб відповісти на це питання, необхідно пригадати, що таке поліморфізм - це здатність сутності приймати різні форми залежно від контексту.
В ООП розрізняють 2 види поліморфізму, статичний та динамічний. Статичний поліморфізм надає змогу використання одного й того ж імені функції/метода для багатьох функцій, які мають різні списки параметрів і/або різні типи повернення. До статичного поліморфізму також відносять шаблони (т.з. дженерики), які дають змогу писати універсальний код, де типи спеціалізує компілятор під час компіляції. При статичному поліморфізмі типи визначаються під час компіляції, отже вибір конкретного варіанта функції або метода залежать від контексту.

**При динамічному поліморфізмі, вибір варіанта метода - визначається підчас виконання програми**, а не компіляції. Це дає змогу об'єктам класів однієї ієрархії реагувати на один й теж виклик метода по різному.
Як це працює абстрактно : 
- Базовий клас визначає метод
- Його дочірні класи його перевизначають (override)
- При виклику метода його реалізація - залежить від об'єкта

**Реалізація в C++ (Таблиця віртуальних методів):**
Технічно C++ реалізує це через **vtable** (таблицю віртуальних функцій). Кожен клас, що має віртуальні методи, має свою приховану статичну таблицю вказівників на ці методи. Кожен об'єкт такого класу містить прихований вказівник **vptr** на цю таблицю. Коли ми викликаємо віртуальний метод через вказівник на базовий клас, програма дивиться в vptr об'єкта, знаходить vtable і викликає правильну функцію.

В С++ методи, які можна перевизначити, позначають ключовим словом **virtual**, а перевизначені методи позначають словом **override**, якщо метод вже має базову поведінку. 

Ось прикладовий код:
```cpp
#include <iostream>

// базовий клас Тварина
class Animal {
public:
    virtual ~Animal() {} // Важливо: віртуальний деструктор

    // базовий метод
    virtual void speak() {
        std::cout << "Базовий звук" << std::endl;
    }
    // чисто віртуальний метод (тварина не вміє какати абстрактно, це робить клас абстрактним)
    virtual void poop() = 0;
};

// нащадок
class Dog : public Animal {
public:
    // override
    void speak() override {
        std::cout << "Гав гав" << std::endl;
    }
    // ключове слово override опціональне, але рекомендоване для уникнення помилок
    void poop() override {
        std::cout << "Как як пук пук" << std::endl;
    }
};

int main() {
    // Поліморфізм працює через вказівники або посилання на базовий клас
    Animal* myPet = new Dog();
    
    // Виклик методу визначається в runtime (vtable lookup)
    myPet->speak(); // Виведе: "Гав гав" (хоча вказівник типу Animal*, об'єкт типу Dog)
    
    delete myPet;
    return 0;
}
```

**Важливе зауваження про деструктори:**
Якщо клас призначений для поліморфного використання (має віртуальні методи), його деструктор **обов'язково** має бути віртуальним (`virtual ~ClassName()`).
Це необхідно для того, щоб при видаленні об'єкта похідного класу через вказівник на базовий клас (`delete myPet;`), викликався деструктор саме похідного класу (`Dog`), а потім базового (`Animal`). Без `virtual` буде викликаний лише деструктор базового класу, що призведе до часткового видалення об'єкта (витік ресурсів) або невизначеної поведінки (undefined behavior).

Узагальнюючи, динамічний поліморфізм, дає змогу писати більш гнучкий та універсальний код, працюючий з ієрархією классів, використовуюючи віртуальні методи.

**PL:**
Tutaj znajdzie się szczegółowe wyjaśnienie pytania po polsku.

---

## Питання 2

**UA:** [Текст питання українською мовою]

**PL:** Jakie można wyróżnić modele procesu tworzenia oprogramowania. Scharakteryzuj niektóre z nich.

### Пояснення / Wyjaśnienie

**UA:**
Моделі процесу створення програмного забезпечення — це формалізовані підходи, які описують, як саме організований життєвий цикл ПЗ: від ідеї та вимог до розробки, тестування і підтримки.
Існують багато моделей процесу створення ПЗ (Програмного Забезпечення), основні :
1. Каскадна модель (Waterfall)
    * Олдскульна і класична модель
    * Етапи йдуть тільки по черзі:
      1. Аналіз вимог
      2. Проєктування
      3. Реалізація
      4. Тестування
      5. Впровадження
      6. Підтримка
    * Перехід на наступний етап можливий лише після закінчення попереднього 
2. V-модель
3. Ітеративна модель
4. Інкрементна модель
5. Спіральна модель
6. Agile (Scrum, Kanban тощо)
**PL:**
Tutaj znajdzie się szczegółowe wyjaśnienie pytania po polsku.

---

## Питання 3

**UA:** [Текст питання українською мовою]

**PL:** Jakie są najprostsze algorytmy generacji liczb losowych z zadanym rozkładem prawdopodobieństwa?

### Пояснення / Wyjaśnienie

**UA:**
Тут буде детальне пояснення до питання українською.

**PL:**
Tutaj znajdzie się szczegółowe wyjaśnienie pytania po polsku.

---

## Питання 4

**UA:** [Текст питання українською мовою]

**PL:** Na wybranych przykładach scharakteryzuj podstawowe typy, struktury i organizacje danych.

### Пояснення / Wyjaśnienie

**UA:**
Тут буде детальне пояснення до питання українською.

**PL:**
Tutaj znajdzie się szczegółowe wyjaśnienie pytania po polsku.

---

## Питання 5

**UA:** [Текст питання українською мовою]

**PL:** Opisz cechy i składowe języka SQL, podaj jego wady i zalety. 

### Пояснення / Wyjaśnienie

**UA:**
Тут буде детальне пояснення до питання українською.

**PL:**
Tutaj znajdzie się szczegółowe wyjaśnienie pytania po polsku.

---

## Питання 6

**UA:** [Текст питання українською мовою]

**PL:** Omów pojęcie semaforów i przedstaw przykłady ich zastosowania. 

### Пояснення / Wyjaśnienie

**UA:**
Тут буде детальне пояснення до питання українською.

**PL:**
Tutaj znajdzie się szczegółowe wyjaśnienie pytania po polsku.

---

## Питання 7

**UA:** [Текст питання українською мовою]

**PL:** Omów przetwarzanie potokowe we współczesnych systemach komputerowych.

### Пояснення / Wyjaśnienie

**UA:**
Тут буде детальне пояснення до питання українською.

**PL:**
Tutaj znajdzie się szczegółowe wyjaśnienie pytania po polsku.

---

## Питання 8

**UA:** [Текст питання українською мовою]

**PL:** Omów/Opisz różnice pomiędzy aproksymacją i interpolacją w kontekście wizualizacji danych.

### Пояснення / Wyjaśnienie

**UA:**
Тут буде детальне пояснення до питання українською.

**PL:**
Tutaj znajdzie się szczegółowe wyjaśnienie pytania po polsku.

---

## Питання 9

**UA:** [Текст питання українською мовою]

**PL:** Proszę omówić budowę i uczenie sztucznej sieci neuronowej wielowarstwowej. 

### Пояснення / Wyjaśnienie

**UA:**
Тут буде детальне пояснення до питання українською.

**PL:**
Tutaj znajdzie się szczegółowe wyjaśnienie pytania po polsku.

---

## Питання 10

**UA:** [Текст питання українською мовою]

**PL:** Proszę omówić model referencyjny sieci komputerowej OSI/ISO.

### Пояснення / Wyjaśnienie

**UA:**
Тут буде детальне пояснення до питання українською.

**PL:**
Tutaj znajdzie się szczegółowe wyjaśnienie pytania po polsku.

---

## Питання 11

**UA:** [Текст питання українською мовою]

**PL:** Proszę omówić translację adresów NAT oraz portów PAT w sieciach TCP/IP.

### Пояснення / Wyjaśnienie

**UA:**
Тут буде детальне пояснення до питання українською.

**PL:**
Tutaj znajdzie się szczegółowe wyjaśnienie pytania po polsku.

---

## Питання 12

**UA:** [Текст питання українською мовою]

**PL:**  Przedstaw sposób definicji typu strukturalnego w języku C++ oraz sposób definicji i korzystania ze zmiennej strukturalnej.

### Пояснення / Wyjaśnienie

**UA:**
Тут буде детальне пояснення до питання українською.

**PL:**
Tutaj znajdzie się szczegółowe wyjaśnienie pytania po polsku.

---

## Питання 13

**UA:** [Текст питання українською мовою]

**PL:** Scharakteryzuj maszynę Turinga, omów jej złożoność oraz podaj różnice i podobieństwa pomiędzy deterministycznym a niedeterministycznym jej wariantem.

### Пояснення / Wyjaśnienie

**UA:**
Тут буде детальне пояснення до питання українською.

**PL:**
Tutaj znajdzie się szczegółowe wyjaśnienie pytania po polsku.

---

## Питання 14

**UA:** [Текст питання українською мовою]

**PL:** Scharakteryzuj diagram klas notacji UML.

### Пояснення / Wyjaśnienie

**UA:**
Тут буде детальне пояснення до питання українською.

**PL:**
Tutaj znajdzie się szczegółowe wyjaśnienie pytania po polsku.

---

## Питання 15

**UA:** [Текст питання українською мовою]

**PL:** Wymień i omów struktury systemów operacyjnych. 

### Пояснення / Wyjaśnienie

**UA:**
Тут буде детальне пояснення до питання українською.

**PL:**
Tutaj znajdzie się szczegółowe wyjaśnienie pytania po polsku.

---

## Питання 16

**UA:** [Текст питання українською мовою]

**PL:** Opisz różnicę pomiędzy algorytmami zachłannymi i dynamicznymi.

### Пояснення / Wyjaśnienie

**UA:**
Тут буде детальне пояснення до питання українською.

**PL:**
Tutaj znajdzie się szczegółowe wyjaśnienie pytania po polsku.


---

# Питання по спеціальності / Pytania zakresowe

## Питання 1 / Pytanie 1

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 2 / Pytanie 2

**UA:** [Текст питання]

**PL:** [Treść pytania]
### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 3 / Pytanie 3

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 4 / Pytanie 4

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 5 / Pytanie 5

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 6 / Pytanie 6

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 7 / Pytanie 7

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 8 / Pytanie 8

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 9 / Pytanie 9

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 10 / Pytanie 10

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 11 / Pytanie 11

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 12 / Pytanie 12

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 13 / Pytanie 13

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 14 / Pytanie 14

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 15 / Pytanie 15

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 16 / Pytanie 16

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 17 / Pytanie 17

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 18 / Pytanie 18

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 19 / Pytanie 19

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 20 / Pytanie 20

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 21 / Pytanie 21

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśление

**UA:**
...

**PL:**
...

---

## Питання 22 / Pytanie 22

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśление

**UA:**
...

**PL:**
...

---

## Питання 23 / Pytanie 23

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśление

**UA:**
...

**PL:**
...

---

## Питання 24 / Pytanie 24

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśление

**UA:**
...

**PL:**
...

---

## Питання 25 / Pytanie 25

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśление

**UA:**
...

**PL:**
...

---

## Питання 26 / Pytanie 26

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśление

**UA:**
...

**PL:**
...

---

## Питання 27 / Pytanie 27

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśление

**UA:**
...

**PL:**
...

---

## Питання 28 / Pytanie 28

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśление

**UA:**
...

**PL:**
...

---

## Питання 29 / Pytanie 29

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśление

**UA:**
...

**PL:**
...

---

## Питання 30 / Pytanie 30

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśление

**UA:**
...

**PL:**
...

---

## Питання 31 / Pytanie 31

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśление

**UA:**
...

**PL:**
...

---

## Питання 32 / Pytanie 32

**UA:** [Текст питання]

**PL:** [Treść pytania]

### Пояснення / Wyjaśление

**UA:**
...

**PL:**
...

---

## Питання 33 / Pytanie 33

**UA:** [Текст питання]

**PL:** [Treść pytania]
### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...