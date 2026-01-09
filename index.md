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

##### Коротка версія (для заучування, 40–60 сек)

- Динамічний поліморфізм — це коли реалізація методу вибирається **під час виконання** (runtime), а не компіляції.
- В C++ це робиться через `virtual` методи: виклик через вказівник/посилання на базовий клас попаде в реалізацію похідного об’єкта.
- Технічно: `vptr` в об’єкті → `vtable` класу → потрібна функція.
- Важливо: якщо клас використовується поліморфно, деструктор базового класу має бути `virtual`, інакше `delete` через базовий вказівник може зламати звільнення ресурсів.
- Приклад: `Animal* a = new Dog(); a->speak();` викликає `Dog::speak()`.

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

##### Wersja krótka (do nauczenia, 40–60 s)

- Polimorfizm dynamiczny: wybór implementacji metody odbywa się **w runtime**, a nie w kompilacji.
- W C++ realizacja przez metody `virtual` i wywołania przez wskaźnik/referencję do klasy bazowej.
- Mechanizm: `vptr` w obiekcie → `vtable` klasy → właściwa funkcja.
- Ważne: w klasach polimorficznych destruktor bazowy powinien być `virtual`, aby `delete` przez wskaźnik bazowy wywołał też destruktor klasy pochodnej.
- Przykład: `Animal* a = new Dog(); a->speak();` wywoła `Dog::speak()`.


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

##### Коротка версія (для заучування, 40–60 сек)

- Модель процесу розробки — це спосіб організації життєвого циклу ПЗ від вимог до підтримки.
- **Waterfall:** етапи послідовні, добре коли вимоги стабільні; мінус — дорогі зміни.
- **V-model:** як Waterfall, але з сильним акцентом на тестування і трасованість “вимога → тест”.
- **Iterative/Incremental:** розробка частинами з раннім фідбеком (ітерації уточнюють, інкременти додають функції).
- **Spiral:** ітерації з фокусом на ризики; **Agile:** короткі спринти/потік, частий фідбек, гнучкість.

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

##### Wersja krótka (do nauczenia, 40–60 s)

- Model procesu wytwarzania oprogramowania opisuje organizację cyklu życia: wymagania → rozwój → testy → wdrożenie → utrzymanie.
- **Waterfall:** sekwencyjny, dobry przy stabilnych wymaganiach; wada: zmiany są drogie.
- **V-model:** jak kaskadowy, ale testowanie planowane równolegle (dobra śledzalność „wymaganie → test”).
- **Iteracyjny/Przyrostowy:** dostarczanie w częściach + wczesny feedback (iteracje dopracowują, przyrosty dodają funkcje).
- **Spiralny:** nacisk na ryzyko; **Agile:** krótkie iteracje/sprinty, częsty feedback i adaptacja.


---

## Питання 3 | Jakie są najprostsze algorytmy generacji liczb losowych z zadanym rozkładem prawdopodobieństwa?

**UA:** Які найпростіші алгоритми генерації випадкових чисел із заданим розподілом імовірності?

**PL:** Jakie są najprostsze algorytmy generacji liczb losowych z zadanym rozkładem prawdopodobieństwa?

### Пояснення / Wyjaśnienie

#### Українською (UA)

Комп'ютери зазвичай генерують **псевдовипадкові** числа (PRNG), найчастіше у вигляді рівномірного розподілу на (0,1):

$$U \sim \mathrm{Uniform}(0,1)$$

Тобто будь-яке значення між 0 і 1 з’являється з однаковою ймовірністю. Далі, щоб отримати **заданий розподіл** для змінної X (нормальний, експоненційний, дискретний тощо), застосовують методи перетворення U у потрібний розподіл.

Найпростіші та найчастіше згадувані алгоритми:

1. Метод інверсії (Inverse Transform Sampling)
    - Працює, якщо відома функція розподілу $F(x)$ (CDF) та її обернена $F^{-1}$.
    - Кроки:
        1) Згенерувати $U \sim \mathrm{Uniform}(0,1)$
        2) Обчислити $X = F^{-1}(U)$
    - Приклади:
        - Для експоненційного розподілу $\mathrm{Exp}(\lambda)$:

         $$X = -\frac{1}{\lambda}\ln(1-U) \quad (\text{часто пишуть також } X = -\tfrac{1}{\lambda}\ln U)$$

    - Для дискретного розподілу $(p_1,\dots,p_n)$ це теж інверсія: рахуємо накопичені суми $C_k = \sum_{i=1}^k p_i$ і беремо найменше $k$, для якого $U \le C_k$.

2. Метод відбору/відкидання (Acceptance–Rejection)
    - Корисний, коли $F^{-1}$ складно знайти, але щільність $f(x)$ можна обчислювати.
    - Ідея: беремо простий розподіл-пропозицію $g(x)$, з якого легко генерувати, та константу $M$ таку, що $f(x) \le M g(x)$ для всіх $x$.
    - Кроки (схема):
         1) Згенерувати $Y \sim g$
         2) Згенерувати $U \sim \mathrm{Uniform}(0,1)$
         3) Прийняти $Y$ як $X$, якщо $U \le \frac{f(Y)}{M g(Y)}$, інакше повторити
    - Плюс: універсальний. Мінус: може бути повільний, якщо M велике (багато відкидань).

3. Метод перетворення (Transformation / Generating by transform)
    - Це ширша категорія: беремо 1 або кілька рівномірних U і через формулу отримуємо X.
    - Класичний приклад для нормального розподілу N(0,1): **Box–Muller**
    Нехай $U_1, U_2 \sim \mathrm{Uniform}(0,1)$, тоді

    $$\begin{aligned}
    Z_1 &= \sqrt{-2\ln U_1}\,\cos(2\pi U_2), \\
    Z_2 &= \sqrt{-2\ln U_1}\,\sin(2\pi U_2)
    \end{aligned}$$

    і $Z_1, Z_2$ мають розподіл $\mathcal{N}(0,1)$.

4. Композиція (Mixture/Composition) для сумішей
    - Якщо розподіл $X$ є сумішшю: $X \sim \sum_i w_i D_i$, де $w_i$ — ваги, а $D_i$ — прості розподіли.
    - Алгоритм: спочатку вибрати індекс i за дискретним розподілом w_i, потім згенерувати X з D_i.

Коротко: базовий «двигун» — $U\sim\mathrm{Uniform}(0,1)$, а найпростіші способи отримати заданий розподіл — інверсія CDF, відкидання (accept-reject) та прямі перетворення (напр., Box–Muller для нормального).

##### Коротка версія (для заучування, 40–60 сек)

- Комп’ютер дає псевдовипадкові числа, базово $U\sim\mathrm{Uniform}(0,1)$; далі перетворюємо $U$ у потрібний розподіл $X$.
- **Інверсія CDF:** якщо знаємо $F$ і $F^{-1}$, то $X = F^{-1}(U)$ (приклад: $X=-\frac{1}{\lambda}\ln(1-U)$ для $\mathrm{Exp}(\lambda)$).
- **Acceptance–Rejection:** кандидат $Y\sim g$, приймаємо якщо $U \le \frac{f(Y)}{Mg(Y)}$.
- **Перетворення:** спеціальні формули, напр. Box–Muller дає $\mathcal{N}(0,1)$.
- **Дискретний випадок:** кумулятивні суми $C_k$ і вибір $k$ за умовою $U\le C_k$.

---

#### Po polsku (PL)

Komputer zwykle nie generuje „prawdziwie” losowych liczb, tylko **pseudolosowe** (PRNG). Typowo najłatwiej uzyskać liczby o rozkładzie jednostajnym na (0,1):

$$U \sim \mathrm{Uniform}(0,1)$$

Następnie, aby wygenerować zmienną losową X o **zadanym rozkładzie** (np. normalnym, wykładniczym, dyskretnym), stosuje się proste metody przekształcenia U.

Najprostsze algorytmy generacji z zadanym rozkładem:

1. Metoda transformacji odwrotnej (Inverse Transform Sampling)
        - Działa, gdy znamy dystrybuantę $F(x)$ oraz potrafimy policzyć jej odwrotność $F^{-1}$.
    - Kroki:
        1) Wylosuj $U \sim \mathrm{Uniform}(0,1)$
        2) Oblicz $X = F^{-1}(U)$
        - Przykład (rozkład wykładniczy $\mathrm{Exp}(\lambda)$):

            $$X = -\frac{1}{\lambda}\ln(1-U) \quad (\text{często także } X = -\tfrac{1}{\lambda}\ln U)$$

        - Dla rozkładu dyskretnego $(p_1,\dots,p_n)$: licz sumy skumulowane $C_k = \sum_{i=1}^k p_i$ i wybierz najmniejsze $k$ takie, że $U \le C_k$.

2. Metoda akceptacji–odrzucenia (Acceptance–Rejection)
    - Przydatna, gdy $F^{-1}$ jest trudna, ale znamy (i umiemy policzyć) gęstość $f(x)$.
    - Wybieramy prosty rozkład propozycji $g(x)$ oraz stałą $M$, taką że $f(x) \le M g(x)$.
    - Kroki:
         1) Wylosuj $Y \sim g$
         2) Wylosuj $U \sim \mathrm{Uniform}(0,1)$
         3) Akceptuj $Y$ jako $X$, jeśli $U \le \frac{f(Y)}{M g(Y)}$, w przeciwnym razie powtórz
    - Zaleta: uniwersalna. Wada: bywa nieefektywna, jeśli odrzucamy dużo prób.

3. Metody transformacyjne (Transformation) dla znanych wzorów
    - Używamy jednej lub kilku zmiennych jednostajnych i wzoru na X.
    - Klasyczny przykład dla N(0,1): **Box–Muller**
    Dla $U_1, U_2 \sim \mathrm{Uniform}(0,1)$:

    $$\begin{aligned}
    Z_1 &= \sqrt{-2\ln U_1}\,\cos(2\pi U_2), \\
    Z_2 &= \sqrt{-2\ln U_1}\,\sin(2\pi U_2)
    \end{aligned}$$

    wtedy $Z_1, Z_2 \sim \mathcal{N}(0,1)$.

4. Metoda kompozycji (Composition) dla mieszanek
    - Jeśli $X$ jest mieszanką rozkładów: $X \sim \sum_i w_i D_i$.
    - Najpierw losujemy indeks i zgodnie z wagami w_i, potem losujemy X z rozkładu D_i.

W skrócie: startujemy od $U\sim\mathrm{Uniform}(0,1)$, a najprostsze drogi do zadanego rozkładu to: transformacja odwrotna, akceptacja–odrzucenie oraz bezpośrednie transformacje (np. Box–Muller dla normalnego).

##### Wersja krótka (do nauczenia, 40–60 s)

- Generator daje liczby pseudolosowe, bazowo $U\sim\mathrm{Uniform}(0,1)$; potem przekształcamy $U$ w zmienną $X$ o żądanym rozkładzie.
- **Transformacja odwrotna:** jeśli znamy $F$ i $F^{-1}$, to $X = F^{-1}(U)$ (np. $X=-\frac{1}{\lambda}\ln(1-U)$ dla $\mathrm{Exp}(\lambda)$).
- **Akceptacja–odrzucenie:** losujemy $Y\sim g$ i akceptujemy, gdy $U \le \frac{f(Y)}{Mg(Y)}$.
- **Transformacje:** gotowe wzory, np. Box–Muller daje $\mathcal{N}(0,1)$.
- **Dyskretny:** sumy skumulowane $C_k$ i wybór $k$ z warunku $U\le C_k$.

---

## Питання 4

**UA:** На вибраних прикладах охарактеризуйте базові типи, структури та організації даних.

**PL:** Na wybranych przykładach scharakteryzuj podstawowe typy, struktury i organizacje danych.

### Пояснення / Wyjaśnienie

#### Українською (UA)
Це питання зводиться до 3 різних понять:

1) **Тип даних** — що саме зберігає змінна і які операції дозволені (а також скільки пам’яті треба).
2) **Структура даних** — як елементи організовані в пам’яті, щоб ефективно виконувати операції (доступ, вставка, пошук тощо).
3) **Організація даних** — як дані розміщують/зберігають на рівні пам’яті або файлів/БД (послідовно, з індексом, через хеш тощо).

**1) Базові типи (приклади)**
- Примітивні: `int`, `float/double`, `bool`, `char`.
- Складені/користувацькі: `struct`, `class`, `enum`, масиви, вказівники/посилання.

Приклад: `int age = 20;` (ціле), `bool ok = true;` (логічний), `char c = 'A';`.

**2) Структури даних (приклади + ключові властивості)**
- **Масив (array)**: елементи одного типу, лежать **послідовно** в пам’яті → доступ за індексом $O(1)$, але вставка всередину часто $O(n)$.
- **Зв’язний список (linked list)**: вузли з вказівниками → вставка/видалення біля відомого вузла $O(1)$, але доступ за індексом $O(n)$.
- **Стек (stack)**: принцип LIFO, операції `push/pop/top` зазвичай $O(1)$.
- **Черга (queue)**: принцип FIFO, операції `push/pop/front` зазвичай $O(1)$.
- **Хеш-таблиця (hash table)**: пошук/вставка “в середньому” $O(1)$, але залежить від хеш-функції й колізій.
- **Дерево (tree)**: ієрархія вузлів (напр. бінарне дерево пошуку, купа/heap).
- **Граф (graph)**: вершини + ребра; не обов’язково ієрархічний (можуть бути цикли). Використовується для мереж, маршрутів, залежностей.

**3) Організація/спосіб зберігання даних (приклади)**
- **Послідовна (sequential)**: записи зберігаються один за одним; добре для потокового читання (лог-файл, CSV).
- **Індексована (indexed)**: окремо є індекс (напр., B-tree/B+tree у БД), який прискорює пошук.
- **Хешована (hashed)**: адреса/“кошик” визначається хешем ключа (хеш-індекси, хеш-таблиці).

##### Коротка версія (для заучування, 40–60 сек)

- Тип даних: що зберігаємо і які операції (напр. `int`, `bool`, `char`, `struct`).
- Структура даних: як організовано елементи для операцій (array $O(1)$ доступ; list $O(1)$ вставка біля вузла; stack LIFO; queue FIFO; hash “середнє” $O(1)$).
- Організація зберігання: послідовно (файли), індексовано (B-tree індекси в БД), хешовано (хеш-таблиці/хеш-індекси).

---

#### Po polsku (PL)
W tym pytaniu warto rozróżnić 3 pojęcia:

1) **Typ danych** — co przechowuje zmienna i jakie operacje są dozwolone (oraz ile pamięci potrzeba).
2) **Struktura danych** — jak elementy są ułożone w pamięci, aby operacje były efektywne (dostęp, wstawianie, wyszukiwanie).
3) **Organizacja danych** — sposób rozmieszczenia/zapisu danych w pamięci lub w plikach/DB (sekwencyjnie, z indeksem, przez hash).

**1) Podstawowe typy (przykłady)**
- Prymitywne: `int`, `float/double`, `bool`, `char`.
- Złożone/użytkownika: `struct`, `class`, `enum`, tablice, wskaźniki/referencje.

**2) Struktury danych (przykłady + cechy)**
- **Tablica (array)**: pamięć ciągła → dostęp po indeksie $O(1)$, ale wstawianie w środku zwykle $O(n)$.
- **Lista (linked list)**: węzły połączone wskaźnikami → wstawianie/usuwanie przy znanym węźle $O(1)$, dostęp po indeksie $O(n)$.
- **Stos (stack)**: LIFO, operacje `push/pop/top` zazwyczaj $O(1)$.
- **Kolejka (queue)**: FIFO, operacje `push/pop/front` zazwyczaj $O(1)$.
- **Tablica mieszająca (hash table)**: wyszukiwanie/wstawianie „średnio” $O(1)$ (zależy od kolizji i funkcji hashującej).
- **Drzewo (tree)**: struktura hierarchiczna (np. BST, heap).
- **Graf (graph)**: wierzchołki i krawędzie; nie musi być hierarchiczny (mogą występować cykle).

**3) Organizacja danych (przykłady)**
- **Sekwencyjna**: rekordy po kolei; dobra do czytania strumieniowego (log/CSV).
- **Indeksowana**: dodatkowa struktura indeksu (np. B-tree/B+tree w bazach danych) przyspiesza wyszukiwanie.
- **Haszowana**: adres/„koszyk” wynika z hasha klucza (hash-index, hash table).

##### Wersja krótka (do nauczenia, 40–60 s)

- Typ danych: co przechowuję i jakie operacje (np. `int`, `bool`, `char`, `struct`).
- Struktury danych: tablica $O(1)$ dostęp, lista $O(n)$ dostęp, stos LIFO, kolejka FIFO, hash „średnio” $O(1)$.
- Organizacja danych: sekwencyjna (pliki), indeksowana (B-tree w DB), haszowana (hash table/indeksy).

---

## Питання 5

**UA:** Опишіть характеристики та складові мови SQL, наведіть її переваги та недоліки.

**PL:** Opisz cechy i składowe języka SQL, podaj jego wady i zalety. 

### Пояснення / Wyjaśnienie

#### Українською (UA)
**SQL (Structured Query Language)** — декларативна мова для роботи з реляційними базами даних: описує *що* потрібно отримати/змінити, а *як* це зробити ефективно, вирішує СУБД (оптимізатор запитів).

**Основні характеристики SQL:**
- Декларативність: ми задаємо умову/результат, а не алгоритм.
- Орієнтація на множини: операції над наборами рядків (таблицями), а не над одиничними значеннями.
- Стандартизованість (ANSI/ISO), але є діалекти (PostgreSQL, MySQL, SQL Server, Oracle).
- Інтеграція з транзакціями: узгодженість змін (ACID у більшості реляційних СУБД).

**Складові/підмови SQL (найчастіше вимагають на екзамені):**
1. **DDL (Data Definition Language)** — визначення структури даних
    - `CREATE`, `ALTER`, `DROP`
    - об’єкти: таблиці, індекси, представлення (views)
2. **DML (Data Manipulation Language)** — робота з даними
    - `SELECT`, `INSERT`, `UPDATE`, `DELETE` (інколи `MERGE`)
3. **DCL (Data Control Language)** — права доступу
    - `GRANT`, `REVOKE`
4. **TCL (Transaction Control Language)** — керування транзакціями
    - `COMMIT`, `ROLLBACK`, `SAVEPOINT`

**Що “всередині” типового запиту SELECT (як компоненти):**
- `SELECT ... FROM ... WHERE ... GROUP BY ... HAVING ... ORDER BY ...`
- З’єднання: `JOIN` (INNER/LEFT/RIGHT/FULL)
- Агрегації: `COUNT`, `SUM`, `AVG`, `MIN`, `MAX`

**Переваги SQL:**
- Швидке формулювання запитів до даних, багато задач вирішуються коротко.
- Оптимізатор СУБД може вибрати ефективний план виконання.
- Потужні можливості: індекси, обмеження цілісності (`PRIMARY KEY`, `FOREIGN KEY`, `UNIQUE`, `CHECK`), транзакції.
- Широко підтримується, легко інтегрується з більшістю мов програмування.

**Недоліки SQL:**
- Діалекти й несумісності між СУБД (працює “не всюди однаково”).
- Для складної бізнес-логіки запити стають важкими для читання/підтримки.
- “Impedance mismatch” між ООП та реляційною моделлю (часто потрібні ORM).
- Масштабування під дуже високі навантаження/розподілені системи може бути складним (хоча залежить від СУБД і архітектури).

##### Коротка версія (для заучування, 40–60 сек)

- SQL — декларативна мова для реляційних БД (описуємо *що*, оптимізацію робить СУБД).
- Складові: **DDL** (`CREATE/ALTER/DROP`), **DML** (`SELECT/INSERT/UPDATE/DELETE`), **DCL** (`GRANT/REVOKE`), **TCL** (`COMMIT/ROLLBACK`).
- SELECT складається з `SELECT-FROM-WHERE-GROUP BY-HAVING-ORDER BY`, є `JOIN` і агрегати.
- Плюси: стандарт, індекси/цілісність/транзакції, оптимізатор.
- Мінуси: діалекти, складні запити важко підтримувати, ООП↔реляційний розрив.

---

#### Po polsku (PL)
**SQL (Structured Query Language)** to język deklaratywny do pracy z relacyjnymi bazami danych: opisujemy *co* chcemy uzyskać lub zmienić, a *jak* to wykonać efektywnie wybiera silnik bazy (optymalizator zapytań).

**Cechy SQL:**
- Deklaratywność i praca na zbiorach (tabelach).
- Standaryzacja (ANSI/ISO), ale w praktyce istnieją dialekty (PostgreSQL, MySQL, SQL Server, Oracle).
- Wsparcie transakcji i spójności danych (ACID w większości RDBMS).

**Składowe/podjęzyki SQL:**
1. **DDL (Data Definition Language)** — definicja struktury
    - `CREATE`, `ALTER`, `DROP`
2. **DML (Data Manipulation Language)** — operacje na danych
    - `SELECT`, `INSERT`, `UPDATE`, `DELETE` (czasem `MERGE`)
3. **DCL (Data Control Language)** — uprawnienia
    - `GRANT`, `REVOKE`
4. **TCL (Transaction Control Language)** — transakcje
    - `COMMIT`, `ROLLBACK`, `SAVEPOINT`

**Typowe elementy zapytania SELECT:**
- `SELECT ... FROM ... WHERE ... GROUP BY ... HAVING ... ORDER BY ...`
- `JOIN` (INNER/LEFT/RIGHT/FULL), agregacje `COUNT/SUM/AVG/MIN/MAX`

**Zalety SQL:**
- Szybkie i czytelne zapytania do danych; bardzo popularny standard.
- Optymalizator może dobrać wydajny plan wykonania.
- Wbudowane mechanizmy: indeksy, ograniczenia integralności (`PRIMARY KEY`, `FOREIGN KEY`, `UNIQUE`, `CHECK`), transakcje.

**Wady SQL:**
- Różnice między dialektami (przenośność bywa ograniczona).
- Bardzo złożone zapytania są trudne w utrzymaniu.
- “Impedance mismatch” OOP vs model relacyjny (często używa się ORM).
- Skalowanie i rozproszenie bywa wyzwaniem (zależy od silnika i architektury).

##### Wersja krótka (do nauczenia, 40–60 s)

- SQL to język deklaratywny dla relacyjnych BD (mówimy *co*, baza wybiera *jak*).
- Podjęzyki: **DDL** (`CREATE/ALTER/DROP`), **DML** (`SELECT/INSERT/UPDATE/DELETE`), **DCL** (`GRANT/REVOKE`), **TCL** (`COMMIT/ROLLBACK`).
- SELECT: `SELECT-FROM-WHERE-GROUP BY-HAVING-ORDER BY`, do tego `JOIN` i agregacje.
- Plusy: standard, optymalizator, indeksy/integralność/transakcje.
- Minusy: dialekty, trudne złożone zapytania, niedopasowanie do OOP.

---

## Питання 6

**UA:** Поясніть поняття семафорів і наведіть приклади їх застосування.

**PL:** Omów pojęcie semaforów i przedstaw przykłady ich zastosowania. 

### Пояснення / Wyjaśnienie

#### Українською (UA)
**Семафор** — це примітив синхронізації, який дозволяє керувати доступом багатьох потоків/процесів до спільного ресурсу.
Класичний семафор має ціле значення (лічильник) і 2 атомарні операції:

- `wait` / `P()` / `down()`:
  - якщо значення $>0$ — зменшує його і пропускає потік;
  - якщо $=0$ — блокує потік до появи ресурсу.
- `signal` / `V()` / `up()`:
  - збільшує значення і, за потреби, розблоковує один із потоків.

**Види семафорів:**
- **Бінарний семафор** (0/1) — фактично схожий на м’ютекс (але м’ютекс зазвичай має “власника” і додаткові гарантії).
- **Лічильний (counting)** — дозволяє одночасно зайти до $N$ потоків (обмеження паралелізму).

**Де застосовують (типові приклади):**
1. **Взаємне виключення (критична секція)**
    - Ідея: перед входом у критичну секцію робимо `wait`, після виходу — `signal`.
    - Приклад: захист доступу до спільного лічильника/черги.
2. **Producer–Consumer (обмежений буфер)**
    - Два семафори “скільки вільних місць” і “скільки елементів”, плюс м’ютекс для самої структури.
3. **Обмеження доступу до ресурсу з лімітом**
    - Наприклад, “максимум 10 одночасних підключень” або “пул з $N$ об’єктів”.

**Проблеми/пастки:**
- Можливі **deadlock** (взаємне блокування) при неправильному порядку захоплення.
- Можлива **starvation** (голодування) без справедливого планування.
- Важливо: `wait/signal` мають бути парними; вихід з критичної секції — гарантований (часто через `try/finally` / RAII).

##### Коротка версія (для заучування, 40–60 сек)

- Семафор — примітив синхронізації з лічильником доступних “дозволів”.
- Операції: `wait(P)` зменшує і може блокувати; `signal(V)` збільшує і може будити.
- Є бінарний (0/1) і лічильний ($N$ дозволів).
- Застосування: критична секція, producer–consumer, лімітування паралельних доступів до ресурсу.
- Ризики: deadlock/starvation при неправильному використанні.

---

#### Po polsku (PL)
**Semafor** to prymityw synchronizacji, który kontroluje dostęp wielu wątków/procesów do współdzielonego zasobu.
Klasycznie jest to licznik całkowity oraz dwie operacje atomowe:

- `wait` / `P()` / `down()`:
    - gdy wartość $>0$ — zmniejsza ją i przepuszcza wątek;
    - gdy $=0$ — blokuje wątek.
- `signal` / `V()` / `up()`:
    - zwiększa wartość i może odblokować oczekujący wątek.

**Rodzaje:**
- **Semafor binarny** (0/1) — podobny do mutexa (mutex zwykle ma właściciela).
- **Semafor zliczający (counting)** — pozwala wejść jednocześnie maksymalnie $N$ wątkom.

**Zastosowania (klasyczne przykłady):**
1. **Sekcja krytyczna** — `wait` przed wejściem, `signal` po wyjściu.
2. **Producer–Consumer (bufor ograniczony)** — semafory “wolne miejsca” i “liczba elementów” + mutex do ochrony struktury.
3. **Limit równoległości** — np. maksymalna liczba jednoczesnych połączeń, pula zasobów.

**Pułapki:**
- **Deadlock** przy złej kolejności blokad.
- **Starvation** (zagłodzenie) przy braku sprawiedliwości.
- `wait/signal` muszą być parą; wyjście z sekcji krytycznej powinno być gwarantowane.

##### Wersja krótka (do nauczenia, 40–60 s)

- Semafor: licznik „pozwoleń” na dostęp do zasobu.
- `wait(P)` zmniejsza i może blokować; `signal(V)` zwiększa i może budzić.
- Rodzaje: binarny (0/1) i zliczający ($N$).
- Zastosowanie: sekcja krytyczna, producer–consumer, limitowanie dostępu.
- Błędy: deadlock/starvation.

---

## Питання 7

**UA:** Поясніть конвеєрну (потокову) обробку в сучасних комп’ютерних системах.

**PL:** Omów przetwarzanie potokowe we współczesnych systemach komputerowych.

### Пояснення / Wyjaśnienie

#### Українською (UA)
**Конвеєрна (потокова) обробка** — це організація виконання, де задача ділиться на послідовні етапи (стадії), і різні “порції” даних/інструкцій проходять ці стадії паралельно (як на виробничому конвеєрі).

Ключова ідея: **зростає пропускна здатність (throughput)**, хоча **затримка (latency)** однієї операції може майже не зменшитися.

**Приклад у процесорах: конвеєр інструкцій (instruction pipeline)**
- Типові стадії: Fetch → Decode → Execute → Memory → Write-back.
- Коли конвеєр “заповнений”, ідеально можна завершувати приблизно 1 інструкцію за такт (залежить від архітектури).

Оцінка виграшу:
- Для $k$ стадій і великої кількості інструкцій $n$ ідеальний приріст близько $\approx k$ (за умови однакової тривалості стадій і відсутності простоїв).

**Проблеми конвеєра (hazards):**
- **Структурні**: конфлікт за ресурс (напр., один порт пам’яті).
- **Дані (data hazards)**: наступна інструкція потребує результат попередньої.
- **Керування (control hazards)**: розгалуження (branch) — не відомо, яка інструкція буде наступною.

**Як це вирішують:**
- **Stall** (простої), **forwarding/bypassing** (перекидання результату), **renaming** (перейменування регістрів), **branch prediction** (передбачення переходів) і спекулятивне виконання.

**Потокова обробка поза CPU (pipeline parallelism):**
- Напр., обробка медіа/даних: читання → декодування → фільтрація → запис.
- Також класичні UNIX-пайпи: команда1 | команда2 | команда3.

##### Коротка версія (для заучування, 40–60 сек)

- Конвеєр — це поділ обчислення на стадії і паралельне проходження різних даних через ці стадії.
- Основний плюс: росте throughput; latency однієї операції майже не обов’язково зменшується.
- Приклад: CPU pipeline Fetch/Decode/Execute/Mem/WB.
- Проблеми: структурні, залежності даних, переходи (branch).
- Рішення: stalls, forwarding, branch prediction.

---

#### Po polsku (PL)
**Przetwarzanie potokowe (pipeline)** polega na podziale zadania na kolejne etapy (stages) i równoległym przetwarzaniu różnych porcji danych/instrukcji na różnych etapach — jak na linii produkcyjnej.

Klucz: rośnie **przepustowość (throughput)**, natomiast **opóźnienie (latency)** pojedynczego elementu nie musi się znacząco zmienić.

**Przykład w CPU: potok instrukcji**
- Typowe fazy: Fetch → Decode → Execute → Memory → Write-back.
- Po „napełnieniu” potoku idealnie można kończyć ok. 1 instrukcję na takt (w uproszczeniu).

**Zysk (intuicyjnie):**
- Dla $k$ etapów i dużego $n$ idealny speedup bywa bliski $\approx k$, jeśli etapy są zbalansowane i nie ma przestojów.

**Zagrożenia (hazards):**
- **Strukturalne**: konflikt o zasób.
- **Danych**: zależności (następna instrukcja czeka na wynik).
- **Sterowania**: skoki/gałęzie (branch).

**Techniki łagodzenia:**
- Stalle, forwarding/bypassing, renaming rejestrów, predykcja skoków i wykonanie spekulacyjne.

**Pipeline poza CPU:**
- Przetwarzanie strumieniowe: np. odczyt → dekodowanie → filtr → zapis.
- Potoki w UNIX: `cmd1 | cmd2 | cmd3`.

##### Wersja krótka (do nauczenia, 40–60 s)

- Potok: etapy + równoległe przetwarzanie różnych danych na różnych etapach.
- Plus: większa przepustowość; latency pojedynczego elementu nie musi spaść.
- Przykład: Fetch/Decode/Execute/Mem/WB.
- Problemy: konflikty zasobów, zależności danych, skoki.
- Rozwiązania: stalle, forwarding, predykcja skoków.

---

## Питання 8

**UA:** [Текст питання українською мовою]

**PL:** Omów/Opisz różnice pomiędzy aproksymacją i interpolacją w kontekście wizualizacji danych.

### Пояснення / Wyjaśnienie

#### Українською (UA)
Тут буде детальне пояснення до питання українською.

---

#### Po polsku (PL)
Tutaj znajdzie się szczegółowe wyjaśnienie pytania po polsku.

---

## Питання 9

**UA:** [Текст питання українською мовою]

**PL:** Proszę omówić budowę i uczenie sztucznej sieci neuronowej wielowarstwowej. 

### Пояснення / Wyjaśnienie

#### Українською (UA)
Тут буде детальне пояснення до питання українською.

---

#### Po polsku (PL)
Tutaj znajdzie się szczegółowe wyjaśnienie pytania po polsku.

---

## Питання 10

**UA:** [Текст питання українською мовою]

**PL:** Proszę omówić model referencyjny sieci komputerowej OSI/ISO.

### Пояснення / Wyjaśnienie

#### Українською (UA)
Тут буде детальне пояснення до питання українською.

---

#### Po polsku (PL)
Tutaj znajdzie się szczegółowe wyjaśnienie pytania po polsku.

---

## Питання 11

**UA:** [Текст питання українською мовою]

**PL:** Proszę omówić translację adresów NAT oraz portów PAT w sieciach TCP/IP.

### Пояснення / Wyjaśnienie

#### Українською (UA)
Тут буде детальне пояснення до питання українською.

---

#### Po polsku (PL)
Tutaj znajdzie się szczegółowe wyjaśnienie pytania po polsku.

---

## Питання 12

**UA:** [Текст питання українською мовою]

**PL:**  Przedstaw sposób definicji typu strukturalnego w języku C++ oraz sposób definicji i korzystania ze zmiennej strukturalnej.

### Пояснення / Wyjaśnienie

#### Українською (UA)
Тут буде детальне пояснення до питання українською.

---

#### Po polsku (PL)
Tutaj znajdzie się szczegółowe wyjaśnienie pytania po polsku.

---

## Питання 13

**UA:** [Текст питання українською мовою]

**PL:** Scharakteryzuj maszynę Turinga, omów jej złożoność oraz podaj różnice i podobieństwa pomiędzy deterministycznym a niedeterministycznym jej wariantem.

### Пояснення / Wyjaśnienie

#### Українською (UA)
Тут буде детальне пояснення до питання українською.

---

#### Po polsku (PL)
Tutaj znajdzie się szczegółowe wyjaśnienie pytania po polsku.

---

## Питання 14

**UA:** [Текст питання українською мовою]

**PL:** Scharakteryzuj diagram klas notacji UML.

### Пояснення / Wyjaśnienie

#### Українською (UA)
Тут буде детальне пояснення до питання українською.

---

#### Po polsku (PL)
Tutaj znajdzie się szczegółowe wyjaśnienie pytania po polsku.

---

## Питання 15

**UA:** [Текст питання українською мовою]

**PL:** Wymień i omów struktury systemów operacyjnych. 

### Пояснення / Wyjaśnienie

#### Українською (UA)
Тут буде детальне пояснення до питання українською.

---

#### Po polsku (PL)
Tutaj znajdzie się szczegółowe wyjaśnienie pytania po polsku.

---

## Питання 16

**UA:** [Текст питання українською мовою]

**PL:** Opisz różnicę pomiędzy algorytmami zachłannymi i dynamicznymi.

### Пояснення / Wyjaśnienie

#### Українською (UA)
Тут буде детальне пояснення до питання українською.

---

#### Po polsku (PL)
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