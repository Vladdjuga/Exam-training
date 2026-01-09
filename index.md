---
---

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

## Зміст / Spis treści

* TOC
{:toc}

# Питання по керунку / Pytania kierunkowe

## Питання 1 | Co to jest polimorfizm dynamiczny. Podaj przykład i omów w jaki sposób w języku C++ ten rodzaj polimorfizmu jest realizowany.

**UA:** Що таке динамічний поліморфізм? Наведіть приклад і обговоріть, як цей вид поліморфізму реалізований у мові C++.

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
Aby odpowiedzieć na to pytanie, trzeba przypomnieć, czym jest polimorfizm: jest to zdolność bytów (np. obiektów) do przyjmowania różnych „form”/zachowań w zależności od kontekstu.
W OOP wyróżnia się dwa rodzaje polimorfizmu: statyczny i dynamiczny. Polimorfizm statyczny pozwala używać tej samej nazwy funkcji/metody dla wielu funkcji o różnych listach parametrów i/lub różnych typach zwracanych. Do polimorfizmu statycznego zalicza się także szablony (tzw. generyki), które umożliwiają pisanie kodu uniwersalnego, a typy są specjalizowane przez kompilator podczas kompilacji. Przy polimorfizmie statycznym wybór konkretnej wersji funkcji/metody zależy od kontekstu i jest rozstrzygany na etapie kompilacji.

**W polimorfizmie dynamicznym wybór wariantu metody jest podejmowany w czasie działania programu**, a nie podczas kompilacji. Dzięki temu obiekty klas w tej samej hierarchii mogą reagować inaczej na to samo wywołanie metody.
Jak to działa w skrócie:
- klasa bazowa definiuje metodę,
- klasy pochodne ją nadpisują (override),
- przy wywołaniu metody jej implementacja zależy od rzeczywistego typu obiektu.

**Realizacja w C++ (tablica metod wirtualnych):**
Technicznie C++ realizuje to przez **vtable** (tablicę funkcji wirtualnych). Każda klasa, która ma metody wirtualne, posiada ukrytą statyczną tablicę wskaźników do tych metod. Każdy obiekt takiej klasy zawiera ukryty wskaźnik **vptr** na tę tablicę. Gdy wywołujemy metodę wirtualną przez wskaźnik do klasy bazowej, program korzysta z vptr obiektu, znajduje odpowiedni wpis w vtable i wywołuje właściwą funkcję.

W C++ metody, które mogą być nadpisywane, oznacza się słowem kluczowym **virtual**, a nadpisane metody często oznacza się słowem **override** (zalecane, żeby uniknąć błędów).

Przykładowy kod:
```cpp
#include <iostream>

// klasa bazowa Animal
class Animal {
public:
    virtual ~Animal() {} // Ważne: destruktor wirtualny

    // metoda bazowa
    virtual void speak() {
        std::cout << "Dźwięk bazowy" << std::endl;
    }

    // czysto wirtualna metoda (brak ogólnej implementacji — klasa staje się abstrakcyjna)
    virtual void poop() = 0;
};

// klasa pochodna
class Dog : public Animal {
public:
    void speak() override {
        std::cout << "Hau hau" << std::endl;
    }

    void poop() override {
        std::cout << "(zachowanie specyficzne dla psa)" << std::endl;
    }
};

int main() {
    // Polimorfizm działa przez wskaźniki lub referencje do klasy bazowej
    Animal* myPet = new Dog();

    // Wywołanie metody jest rozstrzygane w runtime (lookup w vtable)
    myPet->speak(); // wypisze: "Hau hau" (wskaźnik Animal*, obiekt Dog)

    delete myPet;
    return 0;
}
```

**Ważna uwaga o destruktorach:**
Jeśli klasa jest przeznaczona do użycia polimorficznego (ma metody wirtualne), to jej destruktor **musi** być wirtualny (`virtual ~ClassName()`).
To konieczne, żeby przy usuwaniu obiektu klasy pochodnej przez wskaźnik do klasy bazowej (`delete myPet;`) wywołał się destruktor klasy pochodnej (`Dog`), a potem bazowej (`Animal`). Bez `virtual` zwykle wywoła się tylko destruktor klasy bazowej, co może prowadzić do niepełnego zwolnienia zasobów (wyciek) lub niezdefiniowanego zachowania (undefined behavior).

Podsumowując: polimorfizm dynamiczny pozwala pisać bardziej elastyczny i uniwersalny kod pracujący na hierarchii klas dzięki metodom wirtualnym.


---

## Питання 2 | Jakie można wyróżnić modele procesu tworzenia oprogramowania. Scharakteryzuj niektóre z nich.

**UA:** Які можна виділити моделі процесу створення програмного забезпечення? Охарактеризуйте деякі з них.

### Пояснення / Wyjaśnienie

**UA:**
Моделі процесу створення програмного забезпечення — це формалізовані підходи, які описують, як саме організований життєвий цикл ПЗ: від ідеї та вимог до розробки, тестування і підтримки.
Існує багато моделей процесу створення ПЗ (програмного забезпечення), основні:
1. Каскадна модель (Waterfall)
    * <img src="img/waterfall.png" alt="drawing" width="600"/>
    * Класична модель
    * Етапи йдуть тільки по черзі:
      1. Аналіз вимог
      2. Проєктування
      3. Реалізація
      4. Тестування
      5. Впровадження
      6. Підтримка
    * Перехід на наступний етап можливий лише після закінчення попереднього 
    * Зміни на пізніх етапах — це дуже дорого і складно
    * Проста, зрозуміла, але не гнучка і не підходить до складних і динамічних проєктів
    * Коли підходить: коли вимоги стабільні й добре описані на старті (наприклад, типові корпоративні проєкти або регламентовані домени з великою кількістю документації)
    * Плюси: зрозуміле планування, прозорі “контрольні точки”, зручна документація і передбачуваність процесу
    * Мінуси/ризики: пізній фідбек (користувач бачить продукт наприкінці), висока ціна помилок у вимогах, складно реагувати на зміни
2. V-модель
    * <img src="img/v-model.png" alt="drawing" width="600"/>
    * Розширення каскадної моделі, але орієнтована на тестування
    * Кожному етапу розробки відповідає етап тестування
    * Завдяки тестуванню дає змогу підвищити якість ПЗ, але так само як і в каскадній моделі — складно вносити зміни
    * Ключова ідея: верифікація/валідація плануються паралельно — для кожного артефакту (вимоги, дизайн) одразу визначаються відповідні тести
    * Плюси: висока трасованість “вимога → тест”, раннє планування тестування, зменшення ризику пропустити критичні сценарії
    * Коли підходить: системи з високими вимогами до якості та сертифікації (медицина, автомобільна/авіа індустрія тощо)
3. Ітеративна модель
    * <img src="img/iterative.png" alt="drawing" width="600"/>
    * Продукт створюється ітеративно (частинами)
    * Кожна ітерація включає:
      * Аналіз
      * Проєктування
      * Реалізація
      * Тестування
    * Але після кожного циклу - **робоча версія**
    * Переваги: легше вносити зміни і є ранній фідбек. Недоліки: потрібні чітке планування та контроль архітектури, інакше модель складна в підтримці
    * Ключова ідея: ми багаторазово “уточнюємо” продукт, покращуючи існуюче рішення в кожній ітерації (навіть якщо функцій додається небагато)
    * Плюси: раннє виявлення помилок/неправильних припущень, адаптація до змін, поступове уточнення вимог
    * Мінуси/ризики: ризик техборгу без дисципліни, складніше оцінювати кінцевий обсяг робіт, потрібен контроль архітектури й якості
4. Інкрементна модель
    * <img src="img/incremental.png" alt="drawing" width="600"/>
    * В цій моделі функціональність додається поступово, інкрементами
    * Кожен інкремент - нова частина системи, яка додається поверх існуючої
    * Цінність отримується швидко, але знову ж потрібна продумана архітектура
    * Різниця з ітеративною: інкременти здебільшого додають нову функціональність, тоді як ітерації можуть суттєво переробляти/уточнювати вже зроблене
    * Плюси: швидке постачання цінності, пріоритизація функцій, зручніше керувати релізами
    * Мінуси/ризики: проблеми інтеграції між інкрементами, ризик “поганої архітектури”, якщо не закладати фундамент наперед
5. Спіральна модель
    * <img src="img/spiral.png" alt="drawing" width="600"/>
    * Є підвидом ітеративної моделі, що фокусується на виявленні ризиків завчасно
    * Кожен виток спіралі супроводжується:
        1. Планування
        2. Аналіз ризиків
        3. Реалізація (Програмування тощо)
        4. Оцінка результату
    * Підходить для складних систем, де помилки коштують дорого і потрібно мінімізувати ризики, але модель складна і дорога 
    * Ключова ідея: кожний виток починається з аналізу ризиків (технічних, бізнесових, безпекових), часто через прототипування/дослідження
    * Плюси: сильне управління ризиками, краще для високої невизначеності, можна рано відсікати невдалі рішення
    * Мінуси/ризики: висока вартість процесу, потребує досвідченої команди й хорошої культури аналізу ризиків
6. Agile (Scrum, Kanban тощо)
    * <img src="img/agile.png" alt="drawing" width="600"/>
    * Найпопулярніша наразі модель
    * Основна ідея в коротких "спрінтах" (від кількох днів до тижнів), постійному фідбеці від замовника/бізнесу та гнучкості до змін
    * Максимально адаптивна, але складніше точно оцінювати терміни 
    * Ключова ідея: інкрементальна поставка + регулярний зворотний зв’язок (планування, демо, ретроспектива) і пріоритизація задач у беклозі
    * Scrum: фіксовані спринти з визначеною метою; Kanban: без спринтів, фокус на потоці роботи та WIP-лімітах
    * Ризики: без дисципліни легко отримати хаос (часті зміни без контролю, накопичення техборгу), тому потрібні визначення “готово”, якість і прозорі метрики

**PL:**
Modele procesu tworzenia oprogramowania to sformalizowane podejścia opisujące sposób organizacji cyklu życia oprogramowania: od pomysłu i wymagań, przez rozwój, testowanie, aż po utrzymanie.
Istnieje wiele modeli procesu tworzenia oprogramowania, główne z nich to:
1. Model kaskadowy (Waterfall)
    * <img src="img/waterfall.png" alt="drawing" width="600"/>
    * Klasyczny model ("oldschoolowy")
    * Etapy następują po sobie sekwencyjnie:
      1. Analiza wymagań
      2. Projektowanie
      3. Implementacja
      4. Testowanie
      5. Wdrożenie
      6. Utrzymanie
    * Przejście do kolejnego etapu możliwe jest tylko po zakończeniu poprzedniego
    * Zmiany na późnych etapach są bardzo kosztowne i trudne
    * Prosty i zrozumiały, ale mało elastyczny i nieodpowiedni dla złożonych, dynamicznych projektów
    * Kiedy się sprawdza: gdy wymagania są stabilne i dobrze zdefiniowane na początku (dużo dokumentacji, mało zmian)
    * Zalety: łatwe planowanie i kontrola postępu, jasne kamienie milowe, dobra dokumentacja
    * Wady/ryzyka: późny feedback od użytkownika, wysoki koszt zmian, ryzyko nietrafionych wymagań ujawnia się dopiero pod koniec
2. Model V (V-Model)
    * <img src="img/v-model.png" alt="drawing" width="600"/>
    * Rozszerzenie modelu kaskadowego, ale zorientowane na testowanie
    * Każdemu etapowi tworzenia odpowiada etap testowania
    * Dzięki testowaniu pozwala zwiększyć jakość oprogramowania, ale tak jak w modelu kaskadowym - trudno wprowadzać zmiany
    * Klucz: planowanie weryfikacji/walidacji równolegle — do wymagań i projektu od razu przypisuje się testy
    * Zalety: bardzo dobra śledzalność “wymaganie → test”, wysoka jakość i kontrola
    * Kiedy się sprawdza: systemy krytyczne i regulowane (certyfikacja, bezpieczeństwo, medycyna itd.)
3. Model iteracyjny
    * <img src="img/iterative.png" alt="drawing" width="600"/>
    * Produkt tworzony jest iteracyjnie (fragmentami)
    * Każda iteracja zawiera:
      * Analizę
      * Projektowanie
      * Implementację
      * Testowanie
    * Po każdym cyklu powstaje **działająca wersja**
    * Zalety to łatwiejsze wprowadzanie zmian i wczesny feedback, ale wymaga precyzyjnego planowania i kontroli architektury, co czyni ten model trudnym w utrzymaniu
    * Sens: w każdej iteracji dopracowuje się rozwiązanie (często poprawiając to, co już istnieje), na bazie feedbacku
    * Zalety: szybkie wykrywanie błędów i złych założeń, możliwość adaptacji do zmian
    * Ryzyka: bez kontroli łatwo o dług techniczny i “rozjechaną” architekturę
4. Model przyrostowy (inkrementacyjny)
    * <img src="img/incremental.png" alt="drawing" width="600"/>
    * W tym modelu funkcjonalność dodawana jest stopniowo, przyrostami
    * Każdy przyrost to nowa część systemu dodawana do istniejącej
    * Wartość uzyskuje się szybko, ale znów wymagana jest przemyślana architektura
    * Różnica vs iteracyjny: przyrosty częściej dodają nowe funkcje, a iteracje mogą bardziej “udoskonalać” istniejące
    * Zalety: szybkie dostarczanie wartości, łatwiejsze priorytetyzowanie zakresu
    * Ryzyka: problemy integracyjne i architektoniczne, jeśli fundament nie jest zaplanowany
5. Model spiralny
    * <img src="img/spiral.png" alt="drawing" width="600"/>
    * Jest odmianą modelu iteracyjnego, skupiającą się na wczesnym wykrywaniu ryzyka
    * Każdemu obrotowi spirali towarzyszy:
        1. Planowanie
        2. Analiza ryzyka
        3. Realizacja (Programowanie itp.)
        4. Ocena wyniku
    * Odpowiedni dla złożonych systemów, gdzie błąd kosztuje drogo (minimalizuje ryzyko), ale jest skomplikowany i kosztowny
    * Klucz: najpierw identyfikacja i redukcja ryzyk (często prototypem), dopiero potem rozwój
    * Zalety: bardzo dobre zarządzanie ryzykiem, sensowne przy dużej niepewności
    * Wady: kosztowny proces, wymaga doświadczonego zespołu i dobrych praktyk analizy ryzyka
6. Agile (Scrum, Kanban itp.)
    * <img src="img/agile.png" alt="drawing" width="600"/>
    * Obecnie najpopularniejszy model
    * Główna idea to krótkie "sprinty" (od kilku dni do tygodni), stały feedback od klienta/biznesu i elastyczność na zmiany
    * Maksymalnie adaptacyjny, ale trudniej przewidzieć termin zakończenia
    * Klucz: dostarczanie małych przyrostów + ciągły feedback, priorytetyzacja w backlogu, regularne usprawnianie procesu
    * Scrum: sprinty i cele sprintu; Kanban: przepływ pracy, limity WIP i optymalizacja lead time
    * Ryzyka: bez dyscypliny (Definicja Done, jakość, techniczny porządek) Agile może przerodzić się w chaos


---

## Питання 3 | Jakie są najprostsze algorytmy generacji liczb losowych z zadanym rozkładem prawdopodobieństwa?

**UA:** [Текст питання українською мовою]

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

**PL:** Testowanie (rodzaje, poziomy testów) a cykl życia oprogramowania.

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 2 / Pytanie 2

**UA:** [Текст питання]

**PL:** Scharakteryzuj cele i metody testowania jednostkowego.
### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 3 / Pytanie 3

**UA:** [Текст питання]

**PL:** Omów technikę tworzenia oprogramowania Test-Driven Development.

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 4 / Pytanie 4

**UA:** [Текст питання]

**PL:** Omówić typowe funkcje narzędzi wspierających proces debugowania oprogramowania.

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 5 / Pytanie 5

**UA:** [Текст питання]

**PL:** Omówić korzyści z wykorzystania systemu kontroli wersji.

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 6 / Pytanie 6

**UA:** [Текст питання]

**PL:** Omówić sposoby profilowania programów i narzędzia wykorzystywane w tym procesie.

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 7 / Pytanie 7

**UA:** [Текст питання]

**PL:** Porównaj model bare-metal oraz model bazujący na multitaskingu dostarczanym przez RTOS w oprogramowaniu systemów wbudowanych.

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 8 / Pytanie 8

**UA:** [Текст питання]

**PL:** Porównaj metody zapewnienia bezkolizyjnego dostępu do współdzielonych zasobów sprzętowych w RTOS realizowane za pomocą: a) mutexów i b) sekcji krytycznych.

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 9 / Pytanie 9

**UA:** [Текст питання]

**PL:** Wymień i scharakteryzuj metody optymalizacji stron internetowych pod kątem silnika wyszukiwarek

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 10 / Pytanie 10

**UA:** [Текст питання]

**PL:** Architektury aplikacji internetowych.

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 11 / Pytanie 11

**UA:** [Текст питання]

**PL:** Cykl życia aplikacji internetowej

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 12 / Pytanie 12

**UA:** [Текст питання]

**PL:** Sposoby personalizacji aplikacji internetowych.

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 13 / Pytanie 13

**UA:** [Текст питання]

**PL:** Proszę opisać wzorzec projektowy MVC

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 14 / Pytanie 14

**UA:** [Текст питання]

**PL:** Scharakteryzuj strukturę dokumentu HTML.

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 15 / Pytanie 15

**UA:** [Текст питання]

**PL:** Scharakteryzuj rodzaje selektorów CSS.

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 16 / Pytanie 16

**UA:** [Текст питання]

**PL:** Scharakteryzuj podstawowe technologie internetowe działające po stronie klienta.

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 17 / Pytanie 17

**UA:** [Текст питання]

**PL:** Podaj algorytmy wyznaczania powierzchni widocznych oraz omów jeden z nich.

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 18 / Pytanie 18

**UA:** [Текст питання]

**PL:** Omów metodę śledzenia promieni (ray-tracing) oraz podaj jej właściwości.

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 19 / Pytanie 19

**UA:** [Текст питання]

**PL:** Wymień metody modelowania krzywych i powierzchni oraz omów jedną z nich.

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 20 / Pytanie 20

**UA:** [Текст питання]

**PL:** Wymień i scharakteryzuj działanie algorytmów wyszukiwania stron internetowych oraz ustalania ich pozycji w wynikach.

### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...

---

## Питання 21 / Pytanie 21

**UA:** [Текст питання]

**PL:** Wymień dynamiczne diagramy UML używane w projektowaniu systemów informatycznych oraz omów szczegółowo jeden wybrany diagram.

### Пояснення / Wyjaśление

**UA:**
...

**PL:**
...

---

## Питання 22 / Pytanie 22

**UA:** [Текст питання]

**PL:** Omów fazy cyklu życia systemu informatycznego.

### Пояснення / Wyjaśление

**UA:**
...

**PL:**
...

---

## Питання 23 / Pytanie 23

**UA:** [Текст питання]

**PL:** Scharakteryzuj metodykę RUP (Rational Unified Process) wspomagającą proces wytwarzania systemów informatycznych.

### Пояснення / Wyjaśление

**UA:**
...

**PL:**
...

---

## Питання 24 / Pytanie 24

**UA:** [Текст питання]

**PL:** Charakterystyka systemów równoległych z pamięcią współdzieloną i rozproszoną

### Пояснення / Wyjaśление

**UA:**
...

**PL:**
...

---

## Питання 25 / Pytanie 25

**UA:** [Текст питання]

**PL:** Modele i standardy programowania równoległego/rozproszonego dla systemów z pamięcią współdzieloną i rozproszoną.

### Пояснення / Wyjaśление

**UA:**
...

**PL:**
...

---

## Питання 26 / Pytanie 26

**UA:** [Текст питання]

**PL:** Podstawowe problemy programowania współbieżnego, mechanizmy synchronizacji.

### Пояснення / Wyjaśление

**UA:**
...

**PL:**
...

---

## Питання 27 / Pytanie 27

**UA:** [Текст питання]

**PL:** Wymień zasady i scenariusze tworzenia kopii zapasowych.

### Пояснення / Wyjaśление

**UA:**
...

**PL:**
...

---

## Питання 28 / Pytanie 28

**UA:** [Текст питання]

**PL:** Wymień i omów sposoby realizacji macierzy RAID.

### Пояснення / Wyjaśление

**UA:**
...

**PL:**
...

---

## Питання 29 / Pytanie 29

**UA:** [Текст питання]

**PL:** Czym jest system plików? Wymień i opisz trzy wybrane systemy plików.

### Пояснення / Wyjaśление

**UA:**
...

**PL:**
...

---

## Питання 30 / Pytanie 30

**UA:** [Текст питання]

**PL:** Scharakteryzuj architekturę aplikacji zorientowaną na usługi (ang. Service Oriented Architecture)

### Пояснення / Wyjaśление

**UA:**
...

**PL:**
...

---

## Питання 31 / Pytanie 31

**UA:** [Текст питання]

**PL:** Interfejsy funkcyjne i wyrażenia lambda w języku Java. Omów i podaj przykłady.

### Пояснення / Wyjaśление

**UA:**
...

**PL:**
...

---

## Питання 32 / Pytanie 32

**UA:** [Текст питання]

**PL:** Na wybranym przykładzie omów zagadnienie strumieni w języku Java.

### Пояснення / Wyjaśление

**UA:**
...

**PL:**
...

---

## Питання 33 / Pytanie 33

**UA:** [Текст питання]

**PL:** Kolekcje w języku Java. Omów i podaj przykłady ich zastosowania.
### Пояснення / Wyjaśnienie

**UA:**
...

**PL:**
...