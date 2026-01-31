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

5. Дискретний розподіл (Метод «Рулетки»)

    Найпростіший варіант, коли у вас є список варіантів із різними шансами (наприклад: випадіння луту в грі).

    **Алгоритм:**
    1. Складаємо всі ймовірності в масив кумулятивних сум.
    2. Генеруємо число $u \in [0, 1)$.
    3. Дивимося, у який «сектор» потрапило число.

    **Приклад:**
    - Меч (шанс 0.1) $\rightarrow$ поріг 0.1
    - Щит (шанс 0.3) $\rightarrow$ поріг 0.4 ($0.1 + 0.3$)
    - Зілля (шанс 0.6) $\rightarrow$ поріг 1.0 ($0.4 + 0.6$)

    Якщо випало $0.25$ — це потрапляє в інтервал $[0.1, 0.4)$, отже, випав **Щит**.

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

5. Rozkład dyskretny (Metoda „Ruletki")

    Najprostszy wariant, gdy mamy listę opcji z różnymi prawdopodobieństwami (np. wypadanie łupu w grze).

    **Algorytm:**
    1. Tworzymy tablicę sum kumulatywnych wszystkich prawdopodobieństw.
    2. Generujemy liczbę $u \in [0, 1)$.
    3. Sprawdzamy, do którego „sektora" trafiła liczba.

    **Przykład:**
    - Miecz (szansa 0.1) $\rightarrow$ próg 0.1
    - Tarcza (szansa 0.3) $\rightarrow$ próg 0.4 ($0.1 + 0.3$)
    - Mikstura (szansa 0.6) $\rightarrow$ próg 1.0 ($0.4 + 0.6$)

    Jeśli wylosowano $0.25$ — to trafia w przedział $[0.1, 0.4)$, więc wypadła **Tarcza**.

---

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

**Maybe change**

Organizacja danych (Data Organization)
Szersze pojęcie dotyczące sposobu, w jaki dane są uporządkowane, zarządzane i przechowywane w systemach informatycznych. 

Hierarchiczna: Struktura drzewiasta (np. systemy plików).

Relacyjna: Dane w tabelach (wiersze i kolumny).

Plikowa: Sekwencyjna lub indeksowana organizacja rekordów na dysku. 

---

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
**Семафор** — це примітив синхронізації, який дозволяє керувати доступом багатьох потоків/процесів до спільного ресурсу. "ЦЕ ЛІЧИЛЬНИК ДОСТУПНИХ РЕСУРСІВ".
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

---

Теж норм пояснення, типу тут йде мова про те як процесор вибирає інструкції для виконання. Також можна сказати про пайплайн мідлвейрів у ASP.NET але це тільки для обраних.

**Стандартні етапи конвеєра (Classic RISC Pipeline)
Більшість сучасних архітектур використовують поділ інструкції на 5 базових етапів:**

IF (Instruction Fetch): Вибірка інструкції з пам'яті.

ID (Instruction Decode): Декодування інструкції та читання даних з регістрів.

EX (Execute): Виконання операції (наприклад, додавання в АЛП).

MEM (Memory Access): Доступ до пам'яті (якщо потрібно прочитати чи записати дані).

WB (Write Back): Запис результату назад у регістр.

---

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

**UA:** Поясніть різниці між апроксимацією та інтерполяцією в контексті візуалізації даних.

**PL:** Omów/Opisz różnice pomiędzy aproksymacją i interpolacją w kontekście wizualizacji danych.

### Пояснення / Wyjaśnienie

#### Українською (UA)

**Різниця між апроксимацією та інтерполяцією в контексті візуалізації даних**

**Інтерполяція** та **апроксимація** — це два методи, що використовуються для оцінки значень на основі набору відомих точок даних, але вони служать різним цілям у візуалізації даних.

**Інтерполяція:**

- **Мета:** Основна мета інтерполяції — знайти точні значення для відсутніх точок даних, які знаходяться в межах діапазону відомих даних.
- **Принцип:** Інтерполяційна функція (наприклад, лінія або крива) проходить точно через усі наявні точки даних.
- **Використання у візуалізації:** Використовується, коли ви впевнені в точності своїх даних і хочете створити плавний, безперервний графік, що з'єднує всі точки. Наприклад, побудова графіка температури, виміряної в певні моменти часу, щоб показати її безперервну зміну.

**Апроксимація:**

- **Мета:** Мета апроксимації — не пройти через кожну точку, а знайти загальну тенденцію або закономірність у даних, часто для спрощення або згладжування.
- **Принцип:** Апроксимуюча функція (наприклад, лінія тренду) проходить якомога ближче до набору точок даних, але не обов'язково через кожну з них. Вона мінімізує загальну помилку (відстань) між функцією та точками.
- **Використання у візуалізації:** Ідеально підходить для роботи з "зашумленими" або великими наборами даних, де важливо показати загальний тренд, а не дрібні коливання. Класичний приклад — побудова лінії регресії на діаграмі розсіювання для демонстрації зв'язку між двома змінними.

**Ключова відмінність:** Інтерполяція "слухається" даних і проходить через кожну точку, тоді як апроксимація "узагальнює" дані, показуючи їх основний характер.

##### Коротка версія (для заучування, 40–60 сек)

- **Інтерполяція** — метод знаходження значень між відомими точками, крива проходить **точно через всі** точки даних. Використовується для точних даних.
- **Апроксимація** — метод знаходження загального тренду, крива проходить **якомога ближче** до точок, але не обов'язково через них. Використовується для зашумлених даних або виявлення тенденцій.
- Інтерполяція = точність; апроксимація = узагальнення.

---

#### Po polsku (PL)

**Różnice pomiędzy aproksymacją i interpolacją w kontekście wizualizacji danych**

**Interpolacja** i **aproksymacja** to dwie metody używane do szacowania wartości na podstawie zbioru znanych punktów danych, ale służą one różnym celom w wizualizacji danych.

**Interpolacja:**

- **Cel:** Głównym celem interpolacji jest znalezienie dokładnych wartości dla brakujących punktów danych, które znajdują się wewnątrz zakresu znanych danych.
- **Zasada:** Funkcja interpolacyjna (np. linia lub krzywa) przechodzi dokładnie przez wszystkie istniejące punkty danych.
- **Zastosowanie w wizualizacji:** Używana, gdy jesteś pewien dokładności swoich danych i chcesz stworzyć gładki, ciągły wykres łączący wszystkie punkty. Na przykład, tworzenie wykresu temperatury mierzonej w określonych momentach, aby pokazać jej ciągłą zmianę.

**Aproksymacja:**

- **Cel:** Celem aproksymacji nie jest przejście przez każdy punkt, ale znalezienie ogólnej tendencji lub wzorca w danych, często w celu uproszczenia lub wygładzenia.
- **Zasada:** Funkcja aproksymująca (np. linia trendu) przechodzi jak najbliżej zbioru punktów danych, ale niekoniecznie przez każdy z nich. Minimalizuje ona całkowity błąd (odległość) między funkcją a punktami.
- **Zastosowanie w wizualizacji:** Idealna do pracy z "zaszumionymi" lub dużymi zbiorami danych, gdzie ważne jest pokazanie ogólnego trendu, a nie drobnych fluktuacji. Klasycznym przykładem jest narysowanie linii regresji na wykresie rozrzutu, aby zademonstrować związek między dwiema zmiennymi.

**Kluczowa różnica:** Interpolacja "słucha" danych i przechodzi przez każdy punkt, podczas gdy aproksymacja "uogólnia" dane, pokazując ich podstawowy charakter.

##### Wersja krótka (do nauczenia, 40–60 s)

- **Interpolacja** — metoda znajdowania wartości między znanymi punktami, krzywa przechodzi **dokładnie przez wszystkie** punkty danych. Używana dla dokładnych danych.
- **Aproksymacja** — metoda znajdowania ogólnego trendu, krzywa przechodzi **jak najbliżej** punktów, ale niekoniecznie przez nie. Używana dla zaszumionych danych lub wykrywania tendencji.
- Interpolacja = dokładność; aproksymacja = uogólnienie.

---

## Питання 9

**UA:** Будова та навчання штучної нейронної мережі багатошарової.

**PL:** Proszę omówić budowę i uczenie sztucznej sieci neuronowej wielowarstwowej. 

### Пояснення / Wyjaśnienie

#### Українською (UA)

**Будова та навчання штучної нейронної мережі багатошарової (MLP)**

Штучна багатошарова нейронна мережа, також відома як багатошаровий перцептрон (MLP), — це модель, натхненна біологічною структурою мозку, що використовується для вирішення складних завдань, таких як класифікація чи регресія.

**1. Будова (Структура)**

Мережа MLP складається щонайменше з трьох типів шарів нейронів:

- **Вхідний шар (Input Layer):** Не обробляє дані, а лише передає їх у мережу. Кількість нейронів у цьому шарі відповідає кількості ознак (змінних) у вхідних даних.
- **Приховані шари (Hidden Layers):** Один або більше шарів, що знаходяться між вхідним та вихідним шарами. Саме тут відбувається основна обробка даних. Нейрони в цих шарах вчаться виявляти складні патерни та залежності. Кожен нейрон:
  - Отримує сигнали від нейронів попереднього шару.
  - Обчислює зважену суму цих сигналів, додаючи до неї порогове значення (bias).
  - Передає результат через **функцію активації** (наприклад, ReLU, Sigmoid, Tanh), яка вносить нелінійність, дозволяючи мережі вивчати складні функції.
- **Вихідний шар (Output Layer):** Останній шар, що генерує результат. Кількість нейронів та їхня функція активації залежать від завдання:
  - **Регресія:** Зазвичай один нейрон із лінійною функцією активації.
  - **Бінарна класифікація:** Один нейрон із функцією Sigmoid.
  - **Багатокласова класифікація:** `N` нейронів (де `N` — кількість класів) із функцією Softmax.

Нейрони між сусідніми шарами зазвичай з'єднані за принципом "кожен з кожним" (fully-connected).

**2. Навчання (Процес тренування)**

Мета навчання — знайти такі значення ваг та зсувів (bias), щоб мережа генерувала результати, якомога ближчі до очікуваних. Цей процес є ітераційним і базується на алгоритмі **зворотного поширення помилки (backpropagation)**.

Кроки в одній епосі (одному проході через весь набір даних):

1. **Пряме поширення (Forward Propagation):**
   - Вхідні дані подаються на вхідний шар.
   - Сигнал проходить через послідовні приховані шари до вихідного, генеруючи прогноз.

2. **Обчислення помилки (Loss Function):**
   - Прогноз мережі порівнюється з реальним значенням (міткою) за допомогою **функції втрат** (наприклад, середньоквадратична помилка для регресії, перехресна ентропія для класифікації). Результат — це число, яке показує, "наскільки помиляється мережа".

3. **Зворотне поширення (Backward Propagation):**
   - Обчислена помилка поширюється "назад" від вихідного шару до вхідного.
   - На кожному етапі обчислюється **градієнт** функції втрат відносно ваг та зсувів, який вказує, як зміна параметра впливає на помилку.

4. **Оновлення ваг (Optimization):**
   - Ваги та зсуви коригуються у напрямку, протилежному градієнту, щоб мінімізувати помилку. Для цього використовується алгоритм оптимізації, найчастіше **градієнтний спуск (Gradient Descent)** або його варіанти (наприклад, Adam, RMSprop).
   - Ключовим параметром є **швидкість навчання (learning rate)**, яка контролює величину кроку під час оновлення ваг.

Цей процес повторюється протягом багатьох **епох**, доки помилка на валідаційному наборі даних не перестане зменшуватися, що означає, що мережа навчилася узагальнювати патерни з даних.

##### Коротка версія (для заучування, 40–60 сек)

- **MLP** (багатошаровий перцептрон) — модель з вхідним, прихованими та вихідним шарами.
- **Будова:** нейрони з'єднані fully-connected, використовують функції активації (ReLU, Sigmoid, Tanh, Softmax).
- **Навчання:** 1) пряме поширення → прогноз, 2) обчислення помилки (loss), 3) зворотне поширення → градієнти, 4) оновлення ваг (gradient descent).
- Повторюється через епохи до мінімізації помилки.

---

#### Po polsku (PL)

**Budowa i uczenie sztucznej sieci neuronowej wielowarstwowej (MLP)**

Sztuczna sieć neuronowa wielowarstwowa, znana również jako perceptron wielowarstwowy (MLP), to model inspirowany biologiczną strukturą mózgu, używany do rozwiązywania złożonych problemów, takich jak klasyfikacja czy regresja.

**1. Budowa (Struktura)**

Sieć MLP składa się z co najmniej trzech rodzajów warstw neuronów:

- **Warstwa wejściowa (Input Layer):** Nie przetwarza danych, a jedynie przekazuje je do sieci. Liczba neuronów w tej warstwie odpowiada liczbie cech (zmiennych) w danych wejściowych.
- **Warstwy ukryte (Hidden Layers):** Jedna lub więcej warstw znajdujących się między warstwą wejściową a wyjściową. To tutaj zachodzi właściwe przetwarzanie danych. Neurony w tych warstwach uczą się wykrywać złożone wzorce i zależności. Każdy neuron:
  - Odbiera sygnały z neuronów poprzedniej warstwy.
  - Oblicza sumę ważoną tych sygnałów, dodając do niej wartość progową (bias).
  - Przekazuje wynik przez **funkcję aktywacji** (np. ReLU, Sigmoid, Tanh), która wprowadza nieliniowość, pozwalając sieci uczyć się skomplikowanych funkcji.
- **Warstwa wyjściowa (Output Layer):** Ostatnia warstwa, która generuje wynik. Liczba neuronów i ich funkcja aktywacji zależą od zadania:
  - **Regresja:** Zazwyczaj jeden neuron z liniową funkcją aktywacji.
  - **Klasyfikacja binarna:** Jeden neuron z funkcją Sigmoid.
  - **Klasyfikacja wieloklasowa:** `N` neuronów (gdzie `N` to liczba klas) z funkcją Softmax.

Neurony między sąsiednimi warstwami są zazwyczaj połączone na zasadzie "każdy z każdym" (fully-connected).

**2. Uczenie (Proces treningu)**

Celem uczenia jest znalezienie takich wartości wag i biasów, aby sieć generowała wyniki jak najbliższe oczekiwanym. Proces ten jest iteracyjny i opiera się na algorytmie **propagacji wstecznej (backpropagation)**.

Kroki w jednej epoce (jednym przejściu przez cały zbiór danych):

1. **Propagacja w przód (Forward Propagation):**
   - Dane wejściowe są podawane do warstwy wejściowej.
   - Sygnał przechodzi przez kolejne warstwy ukryte aż do warstwy wyjściowej, generując prognozę.

2. **Obliczenie błędu (Loss Function):**
   - Prognoza sieci jest porównywana z rzeczywistą wartością (etykietą) za pomocą **funkcji straty** (np. błąd średniokwadratowy dla regresji, entropia krzyżowa dla klasyfikacji). Wynik to liczba, która mówi, "jak bardzo myli się sieć".

3. **Propagacja wsteczna (Backward Propagation):**
   - Obliczony błąd jest propagowany "wstecz" od warstwy wyjściowej do wejściowej.
   - Na każdym etapie obliczany jest **gradient** funkcji straty względem wag i biasów, który wskazuje, jak zmiana parametru wpływa na błąd.

4. **Aktualizacja wag (Optimization):**
   - Wagi i biasy są korygowane w kierunku przeciwnym do gradientu, aby zminimalizować błąd. Służy do tego algorytm optymalizacji, najczęściej **spadek gradientowy (Gradient Descent)** lub jego warianty (np. Adam, RMSprop).
   - Kluczowym parametrem jest **współczynnik uczenia (learning rate)**, który kontroluje wielkość kroku podczas aktualizacji wag.

Proces ten powtarza się przez wiele **epok**, aż błąd na zbiorze walidacyjnym przestanie maleć, co oznacza, że sieć nauczyła się generalizować wzorce z danych.

##### Wersja krótka (do nauczenia, 40–60 s)

- **MLP** (perceptron wielowarstwowy) — model z warstwą wejściową, ukrytymi i wyjściową.
- **Budowa:** neurony połączone fully-connected, używają funkcji aktywacji (ReLU, Sigmoid, Tanh, Softmax).
- **Uczenie:** 1) propagacja w przód → prognoza, 2) obliczenie błędu (loss), 3) propagacja wsteczna → gradienty, 4) aktualizacja wag (gradient descent).
- Powtarza się przez epoki do minimalizacji błędu.

---

## Питання 10

**UA:** Еталонна модель комп'ютерної мережі OSI/ISO.

**PL:** Proszę omówić model referencyjny sieci komputerowej OSI/ISO.

### Пояснення / Wyjaśnienie

#### Українською (UA)

**Еталонна модель комп'ютерної мережі OSI/ISO**

Модель OSI (Open Systems Interconnection), розроблена ISO (International Organization for Standardization), — це **концептуальна еталонна модель**, яка поділяє процес мережевої комунікації на сім абстрактних рівнів. Її мета — стандартизувати та спростити розуміння того, як різні протоколи та мережеві пристрої взаємодіють між собою. Хоча на практиці домінує простіша модель TCP/IP, OSI залишається ключовим освітнім інструментом.

**Опис семи рівнів моделі OSI (згори донизу):**

**7. Прикладний рівень (Application Layer)**
- **Мета:** Надання інтерфейсу для програм користувача для доступу до мережевих служб.
- **Завдання:** Ідентифікація партнерів по комунікації, визначення доступності ресурсів.
- **Протоколи:** HTTP, FTP, SMTP, DNS, Telnet.
- **Одиниця даних:** Дані (Data).

**6. Рівень представлення (Presentation Layer)**
- **Мета:** "Перетворення" даних між форматом, що використовується програмою, та мережевим форматом.
- **Завдання:** Шифрування, стиснення, перетворення форматів даних (наприклад, з ASCII на EBCDIC).
- **Протоколи:** SSL/TLS (частково), JPEG, MPEG.
- **Одиниця даних:** Дані (Data).

**5. Сеансовий рівень (Session Layer)**
- **Мета:** Управління сеансами (діалогами) між програмами.
- **Завдання:** Встановлення, управління та завершення сеансів; синхронізація (наприклад, контрольні точки для відновлення передачі після збою).
- **Протоколи:** NetBIOS, RPC.
- **Одиниця даних:** Дані (Data).

**4. Транспортний рівень (Transport Layer)**
- **Мета:** Забезпечення надійної комунікації "від кінця до кінця" (end-to-end) між хостами.
- **Завдання:** Сегментація даних, контроль потоку (flow control), контроль помилок. Розрізняє зв'язок зі встановленням з'єднання (надійний, напр. TCP) та без з'єднання (швидкий, напр. UDP).
- **Протоколи:** TCP, UDP.
- **Одиниця даних:** Сегмент (для TCP), Дейтаграма (для UDP).

**3. Мережевий рівень (Network Layer)**
- **Мета:** Визначення найкращого шляху (маршрутизація) для пакетів у мережі та логічна адресація.
- **Завдання:** Маршрутизація, логічна адресація (IP-адреси), фрагментація пакетів.
- **Пристрої:** Маршрутизатори (роутери).
- **Протоколи:** IP, ICMP, OSPF.
- **Одиниця даних:** Пакет (Packet).

**2. Канальний рівень (Data Link Layer)**
- **Мета:** Забезпечення надійної передачі даних між двома безпосередньо з'єднаними вузлами в одній локальній мережі.
- **Завдання:** Фізична адресація (MAC-адреси), виявлення та виправлення помилок на рівні кадру, контроль доступу до середовища (напр. CSMA/CD в Ethernet).
- **Пристрої:** Комутатори (світчі), мости (bridges).
- **Одиниця даних:** Кадр (Frame).

**1. Фізичний рівень (Physical Layer)**
- **Мета:** Передача необроблених бітів через середовище передачі.
- **Завдання:** Визначає фізичні параметри: напругу, типи кабелів, роз'єми (напр. RJ-45), радіочастоти.
- **Пристрої:** Концентратори (хаби), повторювачі (repeaters), кабелі, мережеві карти.
- **Одиниця даних:** Біт.

##### Коротка версія (для заучування, 40–60 сек)

Модель OSI — 7 рівнів мережевої комунікації:
1. **Фізичний** — біти, кабелі, сигнали
2. **Канальний** — кадри, MAC-адреси, комутатори
3. **Мережевий** — пакети, IP-адреси, маршрутизація (роутери)
4. **Транспортний** — сегменти, TCP/UDP, end-to-end
5. **Сеансовий** — управління сеансами
6. **Представлення** — шифрування, стиснення, формати
7. **Прикладний** — HTTP, FTP, SMTP, інтерфейс користувача

Мнемоніка (знизу вгору): **"Фізик Каже: Мережу Треба Серйозно Представити Прикладно"**

---

#### Po polsku (PL)

**Model referencyjny sieci komputerowej OSI/ISO**

Model OSI (Open Systems Interconnection), opracowany przez ISO (International Organization for Standardization), to **koncepcyjny model referencyjny**, który dzieli proces komunikacji sieciowej na siedem abstrakcyjnych warstw. Jego celem jest standaryzacja i ułatwienie zrozumienia, jak różne protokoły i urządzenia sieciowe współpracują ze sobą. Chociaż w praktyce dominuje prostszy model TCP/IP, OSI pozostaje kluczowym narzędziem edukacyjnym.

**Opis siedmiu warstw modelu OSI (od góry do dołu):**

**7. Warstwa Aplikacji (Application Layer)**
- **Cel:** Zapewnia interfejs dla aplikacji użytkownika do korzystania z usług sieciowych.
- **Zadania:** Identyfikacja partnerów komunikacyjnych, określanie dostępności zasobów.
- **Protokoły:** HTTP, FTP, SMTP, DNS, Telnet.
- **Jednostka danych:** Dane (Data).

**6. Warstwa Prezentacji (Presentation Layer)**
- **Cel:** "Tłumaczenie" danych między formatem używanym przez aplikację a formatem sieciowym.
- **Zadania:** Szyfrowanie, kompresja, konwersja formatów danych (np. z ASCII na EBCDIC).
- **Protokoły:** SSL/TLS (częściowo), JPEG, MPEG.
- **Jednostka danych:** Dane (Data).

**5. Warstwa Sesji (Session Layer)**
- **Cel:** Zarządzanie sesjami (dialogami) między aplikacjami.
- **Zadania:** Ustanawianie, zarządzanie i zamykanie sesji; synchronizacja (np. punkty kontrolne, aby wznowić transmisję po awarii).
- **Protokoły:** NetBIOS, RPC.
- **Jednostka danych:** Dane (Data).

**4. Warstwa Transportowa (Transport Layer)**
- **Cel:** Zapewnienie niezawodnej komunikacji "od końca do końca" (end-to-end) między hostami.
- **Zadania:** Segmentacja danych, kontrola przepływu (flow control), kontrola błędów. Rozróżnia komunikację połączeniową (niezawodną, np. TCP) i bezpołączeniową (szybką, np. UDP).
- **Protokoły:** TCP, UDP.
- **Jednostka danych:** Segment (dla TCP), Datagram (dla UDP).

**3. Warstwa Sieciowa (Network Layer)**
- **Cel:** Wyznaczanie najlepszej ścieżki (routing) dla pakietów w sieci i logiczne adresowanie.
- **Zadania:** Routing, adresowanie logiczne (adresy IP), fragmentacja pakietów.
- **Urządzenia:** Routery.
- **Protokoły:** IP, ICMP, OSPF.
- **Jednostka danych:** Pakiet (Packet).

**2. Warstwa Łącza Danych (Data Link Layer)**
- **Cel:** Zapewnienie niezawodnej transmisji danych między dwoma bezpośrednio połączonymi węzłami w tej samej sieci lokalnej.
- **Zadania:** Adresowanie fizyczne (adresy MAC), wykrywanie i korekcja błędów na poziomie ramki, kontrola dostępu do medium (np. CSMA/CD w Ethernet).
- **Urządzenia:** Przełączniki (switche), mosty (bridges).
- **Jednostka danych:** Ramka (Frame).

**1. Warstwa Fizyczna (Physical Layer)**
- **Cel:** Transmisja surowych bitów przez medium transmisyjne.
- **Zadania:** Definiuje parametry fizyczne: napięcia, typy kabli, złącza (np. RJ-45), częstotliwości radiowe.
- **Urządzenia:** Koncentratory (huby), wzmacniaki (repeaters), kable, karty sieciowe.
- **Jednostka danych:** Bit.

##### Wersja krótka (do nauczenia, 40–60 s)

Model OSI — 7 warstw komunikacji sieciowej:
1. **Fizyczna** — bity, kable, sygnały
2. **Łącza danych** — ramki, adresy MAC, switche
3. **Sieciowa** — pakiety, adresy IP, routing (routery)
4. **Transportowa** — segmenty, TCP/UDP, end-to-end
5. **Sesji** — zarządzanie sesjami
6. **Prezentacji** — szyfrowanie, kompresja, formaty
7. **Aplikacji** — HTTP, FTP, SMTP, interfejs użytkownika

Mnemonik (od dołu): **"Fizyk Łapie Sieć, Transportując Sesjami Prawdziwe Aplikacje"**

---

## Питання 11

**UA:** Будь ласка, обговоріть трансляцію адрес NAT та трансляцію портів PAT у мережах TCP/IP.

**PL:** Proszę omówić translację adresów NAT oraz portów PAT w sieciach TCP/IP.

### Пояснення / Wyjaśnienie

#### Українською (UA)

**NAT (Network Address Translation)** та **PAT (Port Address Translation)** — це механізми, що використовуються в мережах TCP/IP для перетворення IP-адрес. Основна мета їх створення — економія публічних (зовнішніх) IPv4-адрес, які є обмеженим ресурсом.

##### 1. NAT (Трансляція мережевих адрес)

**NAT** — це процес, під час якого маршрутизатор або інший мережевий пристрій змінює IP-адреси в заголовках пакетів, що проходять через нього. Найчастіше NAT використовується для перетворення приватних (внутрішніх) IP-адрес на одну або кілька публічних (зовнішніх) IP-адрес.

**Як це працює:**

1. Комп'ютер у локальній мережі з приватною IP-адресою (наприклад, `192.168.1.10`) надсилає пакет в інтернет.
2. Маршрутизатор, що має одну публічну IP-адресу (наприклад, `80.90.100.110`), отримує цей пакет.
3. Маршрутизатор замінює приватну IP-адресу відправника (`192.168.1.10`) на свою публічну IP-адресу (`80.90.100.110`).
4. Пакет надсилається до місця призначення в інтернеті.
5. Коли надходить відповідь, маршрутизатор виконує зворотне перетворення: замінює публічну IP-адресу призначення на відповідну приватну IP-адресу і надсилає пакет комп'ютеру в локальній мережі.

**Приватні діапазони IP-адрес (RFC 1918):**

- `10.0.0.0` – `10.255.255.255`
- `172.16.0.0` – `172.31.255.255`
- `192.168.0.0` – `192.168.255.255`

Ці адреси не маршрутизуються в інтернеті і можуть вільно використовуватися в локальних мережах.

##### 2. PAT (Трансляція портів)

**PAT (Port Address Translation)**, також відомий як **NAT Overload**, є найпоширенішим типом NAT. Він дозволяє **багатьом** пристроям у локальній мережі одночасно виходити в інтернет, використовуючи **одну** публічну IP-адресу.

**Як це працює:**

PAT розширює можливості NAT, додаючи до перетворення не тільки IP-адреси, але й **номери портів**.

1. Два комп'ютери в локальній мережі (наприклад, `192.168.1.10` та `192.168.1.20`) одночасно надсилають запити в інтернет.
2. Маршрутизатор отримує ці пакети. Щоб розрізняти відповіді для кожного з комп'ютерів, він створює унікальні комбінації, змінюючи не тільки IP-адресу, а й вихідний порт.
   - Пакет від `192.168.1.10` з портом `5001` може бути перетворений на `80.90.100.110` з портом `6001`.
   - Пакет від `192.168.1.20` з портом `5002` може бути перетворений на `80.90.100.110` з портом `6002`.
3. Маршрутизатор зберігає ці перетворення у спеціальній таблиці (NAT table).
4. Коли надходить відповідь на порт `6001`, маршрутизатор, заглядаючи в таблицю, знає, що цей пакет призначений для `192.168.1.10`. Аналогічно, відповідь на порт `6002` буде направлена до `192.168.1.20`.

Таким чином, одна публічна IP-адреса може обслуговувати тисячі одночасних з'єднань від різних пристроїв у локальній мережі.

##### Основні відмінності та переваги

| Характеристика | NAT (базовий) | PAT (NAT Overload) |
|:---|:---|:---|
| **Масштабування** | Зазвичай один-до-одного (одна приватна IP → одна публічна IP). | Багато-до-одного (багато приватних IP → одна публічна IP). |
| **Використання портів** | Не завжди використовує зміну портів. | Завжди використовує зміну портів для розрізнення з'єднань. |
| **Економія адрес** | Обмежена. | Дуже висока. Це основний механізм економії IPv4-адрес. |

**Переваги NAT/PAT:**

- **Економія IPv4-адрес:** Головна перевага, що дозволила інтернету функціонувати попри вичерпання вільних адрес.
- **Безпека:** Приховує структуру внутрішньої мережі від зовнішнього світу. За замовчуванням, пристрої ззовні не можуть ініціювати з'єднання з пристроями всередині локальної мережі.

**Недоліки:**

- **Порушення наскрізної моделі (end-to-end):** Деякі протоколи та програми (наприклад, IP-телефонія, деякі онлайн-ігри) погано працюють з NAT, оскільки вони розраховують на пряме з'єднання між пристроями.
- **Ускладнення трасування:** Відстежити шлях пакета стає складніше.

---

#### Po polsku (PL)

**NAT (Network Address Translation)** oraz **PAT (Port Address Translation)** to mechanizmy wykorzystywane w sieciach TCP/IP do translacji adresów IP. Głównym celem ich powstania jest oszczędność publicznych (zewnętrznych) adresów IPv4, które są ograniczonym zasobem.

##### 1. NAT (Translacja adresów sieciowych)

**NAT** to proces, w którym router lub inne urządzenie sieciowe zmienia adresy IP w nagłówkach pakietów przechodzących przez nie. Najczęściej NAT jest wykorzystywany do przekształcania prywatnych (wewnętrznych) adresów IP na jeden lub kilka publicznych (zewnętrznych) adresów IP.

**Jak to działa:**

1. Komputer w sieci lokalnej z prywatnym adresem IP (na przykład `192.168.1.10`) wysyła pakiet do internetu.
2. Router, który ma jeden publiczny adres IP (na przykład `80.90.100.110`), otrzymuje ten pakiet.
3. Router zamienia prywatny adres IP nadawcy (`192.168.1.10`) na swój publiczny adres IP (`80.90.100.110`).
4. Pakiet jest wysyłany do miejsca przeznaczenia w internecie.
5. Gdy nadchodzi odpowiedź, router wykonuje odwrotne przekształcenie: zamienia publiczny adres IP przeznaczenia na odpowiedni prywatny adres IP i wysyła pakiet do komputera w sieci lokalnej.

**Prywatne zakresy adresów IP (RFC 1918):**

- `10.0.0.0` – `10.255.255.255`
- `172.16.0.0` – `172.31.255.255`
- `192.168.0.0` – `192.168.255.255`

Te adresy nie są routowane w internecie i mogą być swobodnie wykorzystywane w sieciach lokalnych.

##### 2. PAT (Translacja portów)

**PAT (Port Address Translation)**, znany również jako **NAT Overload**, jest najczęściej stosowanym typem NAT. Pozwala on **wielu** urządzeniom w sieci lokalnej jednocześnie łączyć się z internetem, wykorzystując **jeden** publiczny adres IP.

**Jak to działa:**

PAT rozszerza możliwości NAT, dodając do translacji nie tylko adresy IP, ale również **numery portów**.

1. Dwa komputery w sieci lokalnej (na przykład `192.168.1.10` i `192.168.1.20`) jednocześnie wysyłają zapytania do internetu.
2. Router otrzymuje te pakiety. Aby rozróżnić odpowiedzi dla każdego z komputerów, tworzy unikalne kombinacje, zmieniając nie tylko adres IP, ale również port wyjściowy.
   - Pakiet od `192.168.1.10` z portem `5001` może być przekształcony na `80.90.100.110` z portem `6001`.
   - Pakiet od `192.168.1.20` z portem `5002` może być przekształcony na `80.90.100.110` z portem `6002`.
3. Router przechowuje te przekształcenia w specjalnej tablicy (NAT table).
4. Gdy nadchodzi odpowiedź na port `6001`, router, zaglądając do tablicy, wie, że ten pakiet jest przeznaczony dla `192.168.1.10`. Analogicznie, odpowiedź na port `6002` zostanie skierowana do `192.168.1.20`.

W ten sposób jeden publiczny adres IP może obsługiwać tysiące jednoczesnych połączeń od różnych urządzeń w sieci lokalnej.

##### Główne różnice i zalety

| Cecha | NAT (podstawowy) | PAT (NAT Overload) |
|:---|:---|:---|
| **Skalowalność** | Zazwyczaj jeden-do-jednego (jeden prywatny IP → jeden publiczny IP). | Wiele-do-jednego (wiele prywatnych IP → jeden publiczny IP). |
| **Wykorzystanie portów** | Nie zawsze wykorzystuje zmianę portów. | Zawsze wykorzystuje zmianę portów do rozróżniania połączeń. |
| **Oszczędność adresów** | Ograniczona. | Bardzo wysoka. To główny mechanizm oszczędzania adresów IPv4. |

**Zalety NAT/PAT:**

- **Oszczędność adresów IPv4:** Główna zaleta, która pozwoliła internetowi funkcjonować pomimo wyczerpania wolnych adresów.
- **Bezpieczeństwo:** Ukrywa strukturę sieci wewnętrznej przed światem zewnętrznym. Domyślnie urządzenia z zewnątrz nie mogą inicjować połączeń z urządzeniami wewnątrz sieci lokalnej.

**Wady:**

- **Naruszenie modelu end-to-end:** Niektóre protokoły i aplikacje (na przykład telefonia IP, niektóre gry online) źle działają z NAT, ponieważ zakładają bezpośrednie połączenie między urządzeniami.
- **Komplikowanie śledzenia:** Śledzenie ścieżki pakietu staje się trudniejsze.

---

## Питання 12

**UA:** Представте спосіб визначення структурного типу в мові C++ та спосіб визначення і використання структурної змінної.

**PL:** Przedstaw sposób definicji typu strukturalnego w języku C++ oraz sposób definicji i korzystania ze zmiennej strukturalnej.

### Пояснення / Wyjaśnienie

#### Українською (UA)

**Структура (struct)** в C++ — це складений тип даних, який дозволяє об'єднати кілька змінних різних типів під одним іменем. Це зручний спосіб для групування пов'язаних даних.

##### 1. Визначення структурного типу (Definicja typu strukturalnego)

Для визначення структури використовується ключове слово `struct`, за яким слідує ім'я типу, а потім у фігурних дужках `{}` перераховуються її члени (змінні).

**Синтаксис:**
```cpp
struct NazwaStruktury {
    typ_danych1 nazwa_zmiennej1;
    typ_danych2 nazwa_zmiennej2;
    // ...
};
```

**Приклад:**

Давайте визначимо структуру `Student`, яка буде зберігати ім'я, вік та середній бал студента.

```cpp
struct Student {
    std::string imie;
    int wiek;
    double srednia_ocen;
};
```

*Цей код визначає "шаблон" для майбутніх змінних типу `Student`, але ще не створює жодної змінної в пам'яті.*

##### 2. Визначення та використання змінної структурного типу (Definicja i korzystanie ze zmiennej strukturalnej)

Після визначення типу структури ми можемо створювати її екземпляри (змінні).

**Створення змінної:**
```cpp
// Створюємо змінну 'student1' типу 'Student'
Student student1;
```

**Доступ до членів структури та їх ініціалізація:**

Доступ до полів структури здійснюється за допомогою **оператора крапки (`.`)**.

```cpp
#include <iostream>
#include <string>

// 1. Визначення типу структури
struct Student {
    std::string imie;
    int wiek;
    double srednia_ocen;
};

int main() {
    // 2. Створення змінної (екземпляра) структури
    Student student1;

    // 3. Присвоєння значень членам структури
    student1.imie = "Jan Kowalski";
    student1.wiek = 21;
    student1.srednia_ocen = 4.5;

    // 4. Використання даних
    std::cout << "Dane studenta:" << std::endl;
    std::cout << "Imię: " << student1.imie << std::endl;
    std::cout << "Wiek: " << student1.wiek << " lat" << std::endl;
    std::cout << "Średnia ocen: " << student1.srednia_ocen << std::endl;

    return 0;
}
```

**Ініціалізація при створенні:**

Змінну можна ініціалізувати одразу при її створенні, використовуючи фігурні дужки.

```cpp
// Ініціалізація за допомогою списку
Student student2 = {"Anna Nowak", 20, 4.8};

// Або у C++11 та новіших версіях:
Student student3{"Piotr Wiśniewski", 22, 4.2};
```

##### 3. Використання вказівників на структури (Korzystanie ze wskaźników na struktury)

При роботі з вказівниками на структури для доступу до їх членів використовується **оператор стрілки (`->`)**.

```cpp
// Створюємо вказівник на структуру Student
Student* wskaznik_na_studenta;

// Присвоюємо вказівнику адресу змінної student2
wskaznik_na_studenta = &student2;

// Доступ до членів через вказівник
std::cout << "\nDane studenta (przez wskaźnik):" << std::endl;
std::cout << "Imię: " << wskaznik_na_studenta->imie << std::endl;
std::cout << "Wiek: " << wskaznik_na_studenta->wiek << std::endl;
std::cout << "Średnia: " << wskaznik_na_studenta->srednia_ocen << std::endl;
```

Оператор `->` є скороченим записом для `(*wskaznik_na_studenta).imie`.

##### Різниця між `struct` та `class` в C++

Основна і практично єдина відмінність полягає у **модифікаторі доступу за замовчуванням**:

- У `struct` всі члени за замовчуванням є **`public`** (публічними).
- У `class` всі члени за замовчуванням є **`private`** (приватними).

За традицією, `struct` використовують для простих об'єктів, що переважно зберігають дані, тоді як `class` — для складніших об'єктів з інкапсульованою логікою та методами.

---

#### Po polsku (PL)

**Struktura (struct)** w C++ to złożony typ danych, który pozwala połączyć kilka zmiennych różnych typów pod jedną nazwą. Jest to wygodny sposób na grupowanie powiązanych danych.

##### 1. Definicja typu strukturalnego

Do zdefiniowania struktury używa się słowa kluczowego `struct`, po którym następuje nazwa typu, a następnie w nawiasach klamrowych `{}` wymienia się jej składowe (zmienne).

**Składnia:**
```cpp
struct NazwaStruktury {
    typ_danych1 nazwa_zmiennej1;
    typ_danych2 nazwa_zmiennej2;
    // ...
};
```

**Przykład:**

Zdefiniujmy strukturę `Student`, która będzie przechowywać imię, wiek i średnią ocen studenta.

```cpp
struct Student {
    std::string imie;
    int wiek;
    double srednia_ocen;
};
```

*Ten kod definiuje "szablon" dla przyszłych zmiennych typu `Student`, ale nie tworzy jeszcze żadnej zmiennej w pamięci.*

##### 2. Definicja i korzystanie ze zmiennej strukturalnej

Po zdefiniowaniu typu struktury możemy tworzyć jej egzemplarze (zmienne).

**Tworzenie zmiennej:**
```cpp
// Tworzymy zmienną 'student1' typu 'Student'
Student student1;
```

**Dostęp do składowych struktury i ich inicjalizacja:**

Dostęp do pól struktury odbywa się za pomocą **operatora kropki (`.`)**.

```cpp
#include <iostream>
#include <string>

// 1. Definicja typu struktury
struct Student {
    std::string imie;
    int wiek;
    double srednia_ocen;
};

int main() {
    // 2. Tworzenie zmiennej (egzemplarza) struktury
    Student student1;

    // 3. Przypisywanie wartości do składowych struktury
    student1.imie = "Jan Kowalski";
    student1.wiek = 21;
    student1.srednia_ocen = 4.5;

    // 4. Wykorzystanie danych
    std::cout << "Dane studenta:" << std::endl;
    std::cout << "Imię: " << student1.imie << std::endl;
    std::cout << "Wiek: " << student1.wiek << " lat" << std::endl;
    std::cout << "Średnia ocen: " << student1.srednia_ocen << std::endl;

    return 0;
}
```

**Inicjalizacja podczas tworzenia:**

Zmienną można zainicjalizować od razu podczas jej tworzenia, używając nawiasów klamrowych.

```cpp
// Inicjalizacja za pomocą listy
Student student2 = {"Anna Nowak", 20, 4.8};

// Lub w C++11 i nowszych wersjach:
Student student3{"Piotr Wiśniewski", 22, 4.2};
```

##### 3. Korzystanie ze wskaźników na struktury

Podczas pracy ze wskaźnikami na struktury do dostępu do ich składowych używa się **operatora strzałki (`->`)**.

```cpp
// Tworzymy wskaźnik na strukturę Student
Student* wskaznik_na_studenta;

// Przypisujemy wskaźnikowi adres zmiennej student2
wskaznik_na_studenta = &student2;

// Dostęp do składowych przez wskaźnik
std::cout << "\nDane studenta (przez wskaźnik):" << std::endl;
std::cout << "Imię: " << wskaznik_na_studenta->imie << std::endl;
std::cout << "Wiek: " << wskaznik_na_studenta->wiek << std::endl;
std::cout << "Średnia: " << wskaznik_na_studenta->srednia_ocen << std::endl;
```

Operator `->` jest skróconym zapisem dla `(*wskaznik_na_studenta).imie`.

##### Różnica między `struct` a `class` w C++

Główna i praktycznie jedyna różnica polega na **domyślnym modyfikatorze dostępu**:

- W `struct` wszystkie składowe domyślnie są **`public`** (publiczne).
- W `class` wszystkie składowe domyślnie są **`private`** (prywatne).

Tradycyjnie `struct` używa się dla prostych obiektów, które głównie przechowują dane, natomiast `class` — dla bardziej złożonych obiektów z hermetyzowaną logiką i metodami.

---

## Питання 13

**UA:** Охарактеризуйте машину Тюрінга, обговоріть її складність та наведіть відмінності і подібності між детерміністичним і недетерміністичним її варіантом.

**PL:** Scharakteryzuj maszynę Turinga, omów jej złożoność oraz podaj różnice i podobieństwa pomiędzy deterministycznym a niedeterministycznym jej wariantem.

### Пояснення / Wyjaśnienie

#### Українською (UA)

**Машина Тюрінга** — це теоретична модель обчислювального пристрою, запропонована Аланом Тюрінгом у 1936 році. Вона є фундаментальним поняттям у теорії алгоритмів та обчислювальної складності, оскільки формалізує поняття алгоритму. Згідно з тезою Черча-Тюрінга, будь-який алгоритм, який можна виконати на реальному комп'ютері, можна також змоделювати на машині Тюрінга.

##### 1. Характеристика Машини Тюрінга (Charakterystyka Maszyny Turinga)

Машина Тюрінга — це абстрактний автомат, що складається з наступних компонентів:

**Нескінченна стрічка (Nieskończona taśma):**

- Розділена на комірки (komórki).
- Кожна комірка може містити один символ із заданого алфавіту стрічки.
- На початку обчислень на стрічці записано вхідне слово, а решта комірок заповнені спеціальним "порожнім" символом.

**Головка читання/запису (Głowica odczytująco-zapisująca):**

- В будь-який момент часу знаходиться над однією з комірок стрічки.
- Може **читати** символ з поточної комірки.
- Може **записувати** новий символ у поточну комірку (затираючи старий).
- Може **рухатися** по стрічці на одну комірку вліво (`L`) або вправо (`R`).

**Керуючий пристрій (Jednostka sterująca):**

- Має **скінченну** множину внутрішніх станів (stany).
- Завжди знаходиться в одному з цих станів.
- Серед станів є виділені: початковий стан (`q_start`), та один або кілька кінцевих (akceptujących) станів.

**Функція переходу (Funkcja przejścia):**

- Це "програма" машини. Вона визначає, що робитиме машина на кожному кроці.
- На основі **поточного стану** та **символу під головкою**, функція переходу визначає:
  1. **Новий стан**, в який перейде машина.
  2. **Символ**, який буде записано в поточну комірку.
  3. **Напрямок руху** головки (вліво або вправо).

**Процес обчислення:**

Машина починає роботу в початковому стані, з головкою на першому символі вхідного слова. На кожному такті вона виконує дію згідно з функцією переходу. Робота завершується, коли машина досягає одного з кінцевих станів. Якщо машина зупинилася в кінцевому стані, вхідне слово вважається "прийнятим" (розпізнаним).

##### 2. Складність (Złożoność)

У контексті машин Тюрінга складність алгоритму вимірюється кількістю ресурсів, необхідних для розв'язання задачі.

- **Часова складність (Złożoność czasowa):** Це кількість кроків (тактів), які машина Тюрінга виконує до зупинки, як функція від довжини вхідних даних (`n`).
- **Просторова складність (Złożoność pamięciowa/przestrzenna):** Це кількість комірок на стрічці, які були використані (відвідані головкою) під час обчислень, як функція від довжини вхідних даних (`n`).

Ці поняття є основою для класифікації алгоритмів та задач (наприклад, класи `P`, `NP`, `PSPACE`).

##### 3. Детерміністичний та Недетерміністичний варіанти (Wariant deterministyczny i niedeterministyczny)

**Детерміністична Машина Тюрінга (DTM - Deterministyczna Maszyna Turinga):**

- Для кожної пари `(поточний стан, символ під головкою)` існує **рівно один** можливий перехід (одна дія).
- Шлях обчислень є унікальним і повністю визначеним.
- Це модель, яка відповідає роботі звичайних комп'ютерів.

**Недетерміністична Машина Тюрінга (NTM - Niedeterministyczna Maszyna Turinga):**

- Для кожної пари `(поточний стан, символ під головкою)` може існувати **кілька** можливих переходів.
- Машина може "розгалужувати" свої обчислення, досліджуючи одночасно кілька шляхів.
- Слово вважається "прийнятим", якщо **хоча б один** із можливих шляхів обчислень приводить до кінцевого стану.

**Подібності:**

- **Обчислювальна потужність:** І DTM, і NTM можуть розпізнавати **один і той самий клас мов** (рекурсивно перелічувані мови). Це означає, що будь-яку задачу, яку може розв'язати NTM, може розв'язати і DTM (і навпаки).

**Відмінності:**

- **Функція переходу:** У DTM вона повертає один набір дій, у NTM — множину можливих дій.
- **Ефективність:** Основна відмінність полягає у складності. Будь-яку NTM можна змоделювати на DTM, але це моделювання може вимагати **експоненційно більше часу**.
  - Якщо NTM розв'язує задачу за поліноміальний час, то відповідна DTM може потребувати експоненційного часу.
- **Концепція:** DTM слідує одному шляху, тоді як NTM можна уявити як машину, що "вгадує" правильний шлях на кожному кроці або паралельно перевіряє всі можливі шляхи.

Проблема **"P проти NP"** — одне з найважливіших відкритих питань в інформатиці — по суті, є питанням про те, чи є DTM та NTM еквівалентними за часовою складністю для поліноміального часу. Тобто, чи можна будь-яку задачу, що швидко *перевіряється* (клас NP, пов'язаний з NTM), так само швидко *розв'язати* (клас P, пов'язаний з DTM).

---

#### Po polsku (PL)

**Maszyna Turinga** to teoretyczny model urządzenia obliczeniowego, zaproponowany przez Alana Turinga w 1936 roku. Jest ona fundamentalnym pojęciem w teorii algorytmów i złożoności obliczeniowej, ponieważ formalizuje pojęcie algorytmu. Zgodnie z tezą Churcha-Turinga, każdy algorytm, który można wykonać na rzeczywistym komputerze, można również zamodelować na maszynie Turinga.

##### 1. Charakterystyka Maszyny Turinga

Maszyna Turinga to abstrakcyjny automat, składający się z następujących komponentów:

**Nieskończona taśma:**

- Podzielona na komórki.
- Każda komórka może zawierać jeden symbol z zadanego alfabetu taśmy.
- Na początku obliczeń na taśmie zapisane jest słowo wejściowe, a pozostałe komórki wypełnione są specjalnym symbolem "pustym".

**Głowica odczytująco-zapisująca:**

- W dowolnym momencie czasu znajduje się nad jedną z komórek taśmy.
- Może **odczytywać** symbol z bieżącej komórki.
- Może **zapisywać** nowy symbol do bieżącej komórki (nadpisując stary).
- Może **poruszać się** po taśmie o jedną komórkę w lewo (`L`) lub w prawo (`R`).

**Jednostka sterująca:**

- Ma **skończony** zbiór stanów wewnętrznych (stany).
- Zawsze znajduje się w jednym z tych stanów.
- Wśród stanów wyróżnione są: stan początkowy (`q_start`) oraz jeden lub kilka stanów końcowych (akceptujących).

**Funkcja przejścia:**

- To "program" maszyny. Określa, co maszyna będzie robić w każdym kroku.
- Na podstawie **bieżącego stanu** i **symbolu pod głowicą**, funkcja przejścia określa:
  1. **Nowy stan**, do którego przejdzie maszyna.
  2. **Symbol**, który zostanie zapisany w bieżącej komórce.
  3. **Kierunek ruchu** głowicy (w lewo lub w prawo).

**Proces obliczeniowy:**

Maszyna rozpoczyna pracę w stanie początkowym, z głowicą na pierwszym symbolu słowa wejściowego. W każdym takcie wykonuje akcję zgodnie z funkcją przejścia. Praca kończy się, gdy maszyna osiągnie jeden ze stanów końcowych. Jeśli maszyna zatrzymała się w stanie końcowym, słowo wejściowe uznaje się za "zaakceptowane" (rozpoznane).

##### 2. Złożoność

W kontekście maszyn Turinga złożoność algorytmu mierzy się liczbą zasobów niezbędnych do rozwiązania zadania.

- **Złożoność czasowa:** To liczba kroków (taktów), które maszyna Turinga wykonuje do zatrzymania, jako funkcja długości danych wejściowych (`n`).
- **Złożoność przestrzenna (pamięciowa):** To liczba komórek na taśmie, które zostały wykorzystane (odwiedzone przez głowicę) podczas obliczeń, jako funkcja długości danych wejściowych (`n`).

Te pojęcia stanowią podstawę do klasyfikacji algorytmów i zadań (np. klasy `P`, `NP`, `PSPACE`).

##### 3. Wariant deterministyczny i niedeterministyczny

**Deterministyczna Maszyna Turinga (DTM):**

- Dla każdej pary `(bieżący stan, symbol pod głowicą)` istnieje **dokładnie jedno** możliwe przejście (jedna akcja).
- Ścieżka obliczeń jest unikalna i całkowicie określona.
- To model odpowiadający działaniu zwykłych komputerów.

**Niedeterministyczna Maszyna Turinga (NTM):**

- Dla każdej pary `(bieżący stan, symbol pod głowicą)` może istnieć **kilka** możliwych przejść.
- Maszyna może "rozgałęziać" swoje obliczenia, badając jednocześnie kilka ścieżek.
- Słowo uznaje się za "zaakceptowane", jeśli **przynajmniej jedna** z możliwych ścieżek obliczeń prowadzi do stanu końcowego.

**Podobieństwa:**

- **Moc obliczeniowa:** Zarówno DTM, jak i NTM mogą rozpoznawać **tę samą klasę języków** (języki rekurencyjnie przeliczalne). Oznacza to, że każde zadanie, które może rozwiązać NTM, może również rozwiązać DTM (i odwrotnie).

**Różnice:**

- **Funkcja przejścia:** W DTM zwraca jeden zestaw akcji, w NTM — zbiór możliwych akcji.
- **Efektywność:** Główna różnica polega na złożoności. Każdą NTM można zasymulować na DTM, ale ta symulacja może wymagać **wykładniczo więcej czasu**.
  - Jeśli NTM rozwiązuje zadanie w czasie wielomianowym, odpowiednia DTM może wymagać czasu wykładniczego.
- **Koncepcja:** DTM podąża jedną ścieżką, podczas gdy NTM można wyobrazić sobie jako maszynę, która "zgaduje" właściwą ścieżkę w każdym kroku lub równolegle sprawdza wszystkie możliwe ścieżki.

Problem **"P versus NP"** — jedno z najważniejszych otwartych pytań w informatyce — jest w istocie pytaniem o to, czy DTM i NTM są równoważne pod względem złożoności czasowej dla czasu wielomianowego. Innymi słowy, czy każde zadanie, które można szybko *zweryfikować* (klasa NP, związana z NTM), można równie szybko *rozwiązać* (klasa P, związana z DTM).

---

## Питання 14

**UA:** Охарактеризуйте діаграму класів нотації UML.

**PL:** Scharakteryzuj diagram klas notacji UML.

### Пояснення / Wyjaśnienie

#### Українською (UA)

**Діаграма класів (Diagram klas)** — це один із найважливіших і найпоширеніших типів діаграм в **UML (Unified Modeling Language)**. Вона належить до структурних діаграм і служить для візуалізації **статичної структури** системи, показуючи її класи, їхні атрибути, методи та зв'язки між ними.

Це, по суті, "креслення" програмної системи, яке допомагає зрозуміти, з яких "цеглинок" вона складається і як ці "цеглинки" взаємодіють між собою.

##### 1. Основні елементи діаграми класів

**Клас (Klasa)**

Клас є центральним елементом діаграми. Він зображується у вигляді **прямокутника**, розділеного на три секції:

1. **Верхня секція: Ім'я класу (Nazwa klasy)**
   - Зазвичай пишеться жирним шрифтом.
   - Якщо клас є *абстрактним* (не можна створити його екземпляр), його ім'я пишеться *курсивом*.

2. **Середня секція: Атрибути (Atrybuty)**
   - Це змінні, що належать класу і описують його властивості.
   - Синтаксис: `видимість назва_атрибута: тип [= значення_за_замовчуванням]`
   - Приклад: `- nazwisko: string`

3. **Нижня секція: Операції (Operacje) / Методи (Metody)**
   - Це функції, які може виконувати клас.
   - Синтаксис: `видимість назва_методу(параметри): тип_повернення`
   - Приклад: `+ obliczWiek(): int`

**Рівні доступу (Poziomy dostępu / Widoczność):**

Кожен атрибут і метод має рівень доступу, що позначається символом:
- `+` **public:** Доступний з будь-якого місця.
- `-` **private:** Доступний тільки всередині цього класу.
- `#` **protected:** Доступний всередині цього класу та в його підкласах.
- `~` **package:** (Рідше використовується) Доступний в межах того ж пакету.

**Приклад класу `Osoba`:**

```
+---------------------------+
|           Osoba           |
+---------------------------+
| - imie: string            |
| - nazwisko: string        |
| # dataUrodzenia: Date     |
+---------------------------+
| + przedstawSie(): void    |
| + obliczWiek(): int       |
+---------------------------+
```

##### 2. Зв'язки між класами (Związki między klasami)

Зв'язки показують, як класи взаємодіють один з одним.

**Асоціація (Asocjacja)**

- **Опис:** Найзагальніший тип зв'язку, що показує, що об'єкти одного класу якимось чином пов'язані з об'єктами іншого.
- **Позначення:** Суцільна лінія (`—`).
- **Приклад:** `Student` асоційований з `Uniwersytet` (студент навчається в університеті).
- **Кратність (Krotność):** Вказує, скільки об'єктів може брати участь у зв'язку.
  - `1` — рівно один
  - `*` — нуль або більше
  - `0..1` — нуль або один
  - `1..*` — один або більше
  - `Student (1..*) --- (1) Uniwersytet` (Багато студентів навчаються в одному університеті).

**Агрегація (Agregacja)**

- **Опис:** Сильніший тип асоціації, що представляє відношення "частина-ціле" (**"has-a"**). Частина може існувати незалежно від цілого.
- **Позначення:** Суцільна лінія з **порожнім ромбом** (`◇—`) з боку "цілого".
- **Приклад:** `Dział` (відділ) складається з `Pracownik` (працівників). Якщо відділ розформують, працівники продовжать існувати.

**Композиція (Kompozycja)**

- **Опис:** Найсильніший тип асоціації, що представляє відношення "частина-ціле", де частина **не може існувати** без цілого. Якщо "ціле" знищується, "частини" також знищуються.
- **Позначення:** Суцільна лінія із **зафарбованим ромбом** (`◆—`) з боку "цілого".
- **Приклад:** `Samochód` (автомобіль) складається з `Silnik` (двигун). Двигун не може існувати поза контекстом конкретного автомобіля.

**Успадкування / Узагальнення (Dziedziczenie / Generalizacja)**

- **Опис:** Представляє відношення **"is-a"** (є). Один клас (підклас/дочірній) успадковує атрибути та методи іншого класу (суперклас/батьківський).
- **Позначення:** Суцільна лінія з **порожньою стрілкою** (`—▷`), що вказує на **суперклас**.
- **Приклад:** `Student` та `Wykładowca` (викладач) є типами `Osoba`.

**Реалізація (Realizacja)**

- **Опис:** Показує, що клас реалізує (виконує контракт) інтерфейсу.
- **Позначення:** Пунктирна лінія з **порожньою стрілкою** (`- - -▷`), що вказує на **інтерфейс**.
- **Приклад:** Клас `Samolot` (літак) реалізує інтерфейс `Latający` (той, що літає).

##### 3. Інтерфейс (Interfejs)

Інтерфейс — це набір операцій (методів) без реалізації. Він визначає контракт, який класи можуть зобов'язатися виконувати.

**Позначення:** Прямокутник з ключовим словом `<<interface>>` над назвою.

##### Навіщо використовувати діаграми класів?

- **Проектування:** Допомагають архітекторам і розробникам спроектувати структуру системи перед написанням коду.
- **Документація:** Служать як чітка і зрозуміла документація існуючої системи.
- **Комунікація:** Полегшують обговорення структури системи між членами команди (включаючи нетехнічних фахівців).
- **Генерація коду:** Існують інструменти, які можуть автоматично генерувати "скелет" коду на основі діаграми класів.

---

#### Po polsku (PL)

**Diagram klas** to jeden z najważniejszych i najpopularniejszych typów diagramów w **UML (Unified Modeling Language)**. Należy do diagramów strukturalnych i służy do wizualizacji **statycznej struktury** systemu, pokazując jego klasy, ich atrybuty, metody oraz związki między nimi.

To w istocie "rysunek techniczny" systemu programowego, który pomaga zrozumieć, z jakich "klocków" się składa i jak te "klocki" ze sobą współdziałają.

##### 1. Podstawowe elementy diagramu klas

**Klasa**

Klasa jest centralnym elementem diagramu. Jest przedstawiana w postaci **prostokąta** podzielonego na trzy sekcje:

1. **Górna sekcja: Nazwa klasy**
   - Zazwyczaj pisana jest czcionką pogrubioną.
   - Jeśli klasa jest *abstrakcyjna* (nie można stworzyć jej instancji), jej nazwa pisana jest *kursywą*.

2. **Środkowa sekcja: Atrybuty**
   - To zmienne należące do klasy i opisujące jej właściwości.
   - Składnia: `widoczność nazwa_atrybutu: typ [= wartość_domyślna]`
   - Przykład: `- nazwisko: string`

3. **Dolna sekcja: Operacje / Metody**
   - To funkcje, które może wykonywać klasa.
   - Składnia: `widoczność nazwa_metody(parametry): typ_zwracany`
   - Przykład: `+ obliczWiek(): int`

**Poziomy dostępu (Widoczność):**

Każdy atrybut i metoda ma poziom dostępu, oznaczany symbolem:
- `+` **public:** Dostępny z dowolnego miejsca.
- `-` **private:** Dostępny tylko wewnątrz tej klasy.
- `#` **protected:** Dostępny wewnątrz tej klasy oraz w jej podklasach.
- `~` **package:** (Rzadziej używany) Dostępny w obrębie tego samego pakietu.

**Przykład klasy `Osoba`:**

```
+---------------------------+
|           Osoba           |
+---------------------------+
| - imie: string            |
| - nazwisko: string        |
| # dataUrodzenia: Date     |
+---------------------------+
| + przedstawSie(): void    |
| + obliczWiek(): int       |
+---------------------------+
```

##### 2. Związki między klasami

Związki pokazują, jak klasy współdziałają ze sobą.

**Asocjacja**

- **Opis:** Najbardziej ogólny typ związku, pokazujący, że obiekty jednej klasy są w jakiś sposób powiązane z obiektami drugiej.
- **Oznaczenie:** Linia ciągła (`—`).
- **Przykład:** `Student` jest powiązany z `Uniwersytet` (student studiuje na uniwersytecie).
- **Krotność:** Określa, ile obiektów może uczestniczyć w związku.
  - `1` — dokładnie jeden
  - `*` — zero lub więcej
  - `0..1` — zero lub jeden
  - `1..*` — jeden lub więcej
  - `Student (1..*) --- (1) Uniwersytet` (Wielu studentów studiuje na jednym uniwersytecie).

**Agregacja**

- **Opis:** Silniejszy typ asocjacji, reprezentujący relację "część-całość" (**"has-a"**). Część może istnieć niezależnie od całości.
- **Oznaczenie:** Linia ciągła z **pustym rombem** (`◇—`) po stronie "całości".
- **Przykład:** `Dział` składa się z `Pracownik`. Jeśli dział zostanie zlikwidowany, pracownicy nadal będą istnieć.

**Kompozycja**

- **Opis:** Najsilniejszy typ asocjacji, reprezentujący relację "część-całość", gdzie część **nie może istnieć** bez całości. Gdy "całość" zostaje zniszczona, "części" również są niszczone.
- **Oznaczenie:** Linia ciągła z **wypełnionym rombem** (`◆—`) po stronie "całości".
- **Przykład:** `Samochód` składa się z `Silnik`. Silnik nie może istnieć poza kontekstem konkretnego samochodu.

**Dziedziczenie / Generalizacja**

- **Opis:** Reprezentuje relację **"is-a"** (jest). Jedna klasa (podklasa/potomna) dziedziczy atrybuty i metody innej klasy (nadklasa/rodzic).
- **Oznaczenie:** Linia ciągła z **pustą strzałką** (`—▷`), wskazującą na **nadklasę**.
- **Przykład:** `Student` i `Wykładowca` są typami `Osoba`.

**Realizacja**

- **Opis:** Pokazuje, że klasa realizuje (wykonuje kontrakt) interfejsu.
- **Oznaczenie:** Linia przerywana z **pustą strzałką** (`- - -▷`), wskazującą na **interfejs**.
- **Przykład:** Klasa `Samolot` realizuje interfejs `Latający`.

##### 3. Interfejs

Interfejs to zbiór operacji (metod) bez implementacji. Definiuje kontrakt, który klasy mogą zobowiązać się wykonać.

**Oznaczenie:** Prostokąt ze słowem kluczowym `<<interface>>` nad nazwą.

##### Po co używać diagramów klas?

- **Projektowanie:** Pomagają architektom i programistom zaprojektować strukturę systemu przed napisaniem kodu.
- **Dokumentacja:** Służą jako czysta i zrozumiała dokumentacja istniejącego systemu.
- **Komunikacja:** Ułatwiają dyskusję o strukturze systemu między członkami zespołu (w tym osobami nietechnicznymi).
- **Generowanie kodu:** Istnieją narzędzia, które mogą automatycznie generować "szkielet" kodu na podstawie diagramu klas.

---

## Питання 15

**UA:** Перерахуйте та обговоріть структури операційних систем.

**PL:** Wymień i omów struktury systemów operacyjnych. 

### Пояснення / Wyjaśnienie

#### Українською (UA)

Структура операційної системи (ОС) визначає, як її компоненти (ядро, драйвери, файлові системи, планувальник процесів тощо) організовані та взаємодіють між собою. Вибір архітектури впливає на продуктивність, безпеку, надійність та гнучкість системи.

Ось основні структури операційних систем:

##### 1. Монолітна структура (Struktura monolityczna)

Це найстаріша і найпростіша архітектура.

**Опис:** Вся операційна система (включаючи ядро, керування пам'яттю, файлову систему, драйвери пристроїв) працює як єдина велика програма в просторі ядра (kernel space). Всі компоненти тісно пов'язані і можуть безпосередньо викликати функції один одного.

**Переваги:**
- **Висока продуктивність:** Взаємодія між компонентами відбувається через прості виклики функцій, що є дуже швидким.

**Недоліки:**
- **Складність розробки та підтримки:** Величезна кодова база, де все пов'язано з усім.
- **Низька надійність:** Помилка в одному компоненті (наприклад, у драйвері) може призвести до збою всієї системи.
- **Проблеми з безпекою:** Всі компоненти працюють на найвищому рівні привілеїв.

**Приклади:** MS-DOS, ранні версії UNIX, Linux (хоча сучасний Linux є *модульним монолітом*, що дозволяє динамічно завантажувати та вивантажувати модулі, це пом'якшує деякі недоліки).

##### 2. Багаторівнева (шарувата) структура (Struktura warstwowa)

**Опис:** ОС організована у вигляді ієрархії шарів (layers). Кожен шар надає певні послуги тільки для вищого шару і використовує послуги тільки нижчого шару. Найнижчий шар (Layer 0) взаємодіє безпосередньо з апаратним забезпеченням, а найвищий (Layer N) — з користувацьким інтерфейсом.

**Переваги:**
- **Простота проектування та тестування:** Кожен шар можна розробляти та перевіряти незалежно.
- **Чітка структура:** Спрощує розуміння системи.

**Недоліки:**
- **Низька продуктивність:** Кожен виклик від вищого до нижчого шару проходить через кілька проміжних шарів, що додає накладні витрати.
- **Складність визначення шарів:** Важко чітко розмежувати функціональність по шарах.

**Приклади:** THE, MULTICS. Ця структура мала великий теоретичний вплив, але рідко використовується в чистому вигляді.

##### 3. Мікроядрова структура (Struktura mikrojądra)

**Опис:** Ядро (kernel) зводиться до абсолютного мінімуму. Воно відповідає лише за найбазовіші функції: керування процесами (планування), керування пам'яттю та механізми міжпроцесної взаємодії (IPC - Inter-Process Communication). Усі інші сервіси (файлові системи, драйвери, мережевий стек) виносяться з ядра і працюють як окремі процеси в просторі користувача (user space).

**Переваги:**
- **Висока надійність та безпека:** Збій у драйвері або файловій системі не призведе до падіння всієї ОС, а лише до перезапуску відповідного сервісу. Сервіси працюють з меншими привілеями.
- **Гнучкість та розширюваність:** Легко додавати нові сервіси, не змінюючи ядро.

**Недоліки:**
- **Низька продуктивність:** Взаємодія між сервісами (які тепер є окремими процесами) відбувається через повільніші механізми IPC, а не через прямі виклики функцій, як у моноліті.

**Приклади:** QNX, Minix, L4, ядро Mach (основа для macOS та iOS, хоча вони є гібридними).

##### 4. Гібридна структура (Struktura hybrydowa)

**Опис:** Ця архітектура поєднує переваги монолітної та мікроядерної структур. Вона має невелике ядро, схоже на мікроядро, але для підвищення продуктивності деякі критично важливі сервіси (наприклад, файлова система або графічна підсистема) працюють у просторі ядра, а менш критичні — у просторі користувача.

**Переваги:**
- **Хороший баланс** між продуктивністю (як у моноліті) та надійністю/гнучкістю (як у мікроядрі).

**Недоліки:**
- Може успадковувати недоліки обох підходів, хоча і в меншій мірі.

**Приклади:** Windows NT (і всі сучасні версії Windows), macOS, iOS. Це найпоширеніша архітектура в сучасних комерційних ОС.

##### 5. Віртуальні машини (Maszyny wirtualne)

**Опис:** Хоча це скоріше концепція, її можна розглядати як структуру. Гіпервізор (монітор віртуальних машин) створює апаратну абстракцію, дозволяючи запускати на одному фізичному комп'ютері кілька екземплярів різних операційних систем. Кожна ОС працює у своїй ізольованій "віртуальній машині".

**Переваги:**
- **Повна ізоляція:** Проблеми в одній гостьовій ОС ніяк не впливають на інші.
- **Гнучкість:** Можливість запускати різні ОС на одному обладнанні.

**Недоліки:**
- **Накладні витрати:** Віртуалізація споживає додаткові ресурси процесора та пам'яті.

**Приклади:** VMware, Hyper-V, KVM.

---

#### Po polsku (PL)

Struktura systemu operacyjnego (SO) określa, jak jego komponenty (jądro, sterowniki, systemy plików, planista procesów itp.) są zorganizowane i współdziałają ze sobą. Wybór architektury wpływa na wydajność, bezpieczeństwo, niezawodność i elastyczność systemu.

Oto główne struktury systemów operacyjnych:

##### 1. Struktura monolityczna

To najstarsza i najprostsza architektura.

**Opis:** Cały system operacyjny (w tym jądro, zarządzanie pamięcią, system plików, sterowniki urządzeń) działa jako jeden wielki program w przestrzeni jądra (kernel space). Wszystkie komponenty są ściśle powiązane i mogą bezpośrednio wywoływać funkcje innych komponentów.

**Zalety:**
- **Wysoka wydajność:** Interakcja między komponentami odbywa się poprzez proste wywołania funkcji, co jest bardzo szybkie.

**Wady:**
- **Złożoność rozwoju i utrzymania:** Ogromna baza kodu, gdzie wszystko jest powiązane ze wszystkim.
- **Niska niezawodność:** Błąd w jednym komponencie (np. w sterowniku) może doprowadzić do awarii całego systemu.
- **Problemy z bezpieczeństwem:** Wszystkie komponenty działają na najwyższym poziomie uprawnień.

**Przykłady:** MS-DOS, wczesne wersje UNIX, Linux (chociaż współczesny Linux jest *modularnym monolitem*, co pozwala dynamicznie ładować i wyładowywać moduły, łagodzi to niektóre wady).

##### 2. Struktura warstwowa

**Opis:** SO jest zorganizowany w postaci hierarchii warstw (layers). Każda warstwa udostępnia określone usługi tylko dla wyższej warstwy i korzysta z usług tylko niższej warstwy. Najniższa warstwa (Layer 0) współdziała bezpośrednio ze sprzętem, a najwyższa (Layer N) — z interfejsem użytkownika.

**Zalety:**
- **Prostota projektowania i testowania:** Każdą warstwę można rozwijać i testować niezależnie.
- **Przejrzysta struktura:** Ułatwia zrozumienie systemu.

**Wady:**
- **Niska wydajność:** Każde wywołanie z wyższej do niższej warstwy przechodzi przez kilka warstw pośrednich, co dodaje narzutu.
- **Złożoność definiowania warstw:** Trudno jest wyraźnie rozgraniczyć funkcjonalność między warstwami.

**Przykłady:** THE, MULTICS. Ta struktura miała duży wpływ teoretyczny, ale rzadko jest używana w czystej postaci.

##### 3. Struktura mikrojądra

**Opis:** Jądro (kernel) jest zredukowane do absolutnego minimum. Odpowiada tylko za najbardziej podstawowe funkcje: zarządzanie procesami (planowanie), zarządzanie pamięcią i mechanizmy komunikacji międzyprocesowej (IPC - Inter-Process Communication). Wszystkie inne usługi (systemy plików, sterowniki, stos sieciowy) są wynoszone z jądra i działają jako oddzielne procesy w przestrzeni użytkownika (user space).

**Zalety:**
- **Wysoka niezawodność i bezpieczeństwo:** Awaria sterownika lub systemu plików nie doprowadzi do upadku całego SO, a tylko do restartu odpowiedniej usługi. Usługi działają z mniejszymi uprawnieniami.
- **Elastyczność i rozszerzalność:** Łatwo dodawać nowe usługi bez zmiany jądra.

**Wady:**
- **Niska wydajność:** Interakcja między usługami (które są teraz oddzielnymi procesami) odbywa się poprzez wolniejsze mechanizmy IPC, a nie poprzez bezpośrednie wywołania funkcji, jak w monoliecie.

**Przykłady:** QNX, Minix, L4, jądro Mach (podstawa dla macOS i iOS, chociaż są one hybrydowe).

##### 4. Struktura hybrydowa

**Opis:** Ta architektura łączy zalety struktur monolitycznej i mikrojądra. Ma małe jądro, podobne do mikrojądra, ale dla zwiększenia wydajności niektóre krytyczne usługi (np. system plików lub podsystem graficzny) działają w przestrzeni jądra, a mniej krytyczne — w przestrzeni użytkownika.

**Zalety:**
- **Dobry balans** między wydajnością (jak w monoliecie) a niezawodnością/elastycznością (jak w mikrojądrze).

**Wady:**
- Może dziedziczyć wady obu podejść, choć w mniejszym stopniu.

**Przykłady:** Windows NT (i wszystkie nowoczesne wersje Windows), macOS, iOS. To najpopularniejsza architektura we współczesnych komercyjnych SO.

##### 5. Maszyny wirtualne

**Opis:** Chociaż jest to raczej koncepcja, można ją rozpatrywać jako strukturę. Hiperwizor (monitor maszyn wirtualnych) tworzy abstrakcję sprzętową, pozwalając uruchomić na jednym fizycznym komputerze kilka instancji różnych systemów operacyjnych. Każdy SO działa we własnej izolowanej "maszynie wirtualnej".

**Zalety:**
- **Pełna izolacja:** Problemy w jednym systemie gościa nie wpływają w żaden sposób na inne.
- **Elastyczność:** Możliwość uruchamiania różnych systemów operacyjnych na tym samym sprzęcie.

**Wady:**
- **Narzut:** Wirtualizacja zużywa dodatkowe zasoby procesora i pamięci.

**Przykłady:** VMware, Hyper-V, KVM.

---

## Питання 16

**UA:** Опишіть різницю між жадібними та динамічними алгоритмами.

**PL:** Opisz różnicę pomiędzy algorytmami zachłannymi i dynamicznymi.

### Пояснення / Wyjaśnienie

#### Українською (UA)

**Жадібні алгоритми (Algorytmy zachłanne)** та **динамічне програмування (programowanie dynamiczne)** — це два підходи до розв'язання оптимізаційних задач. Хоча обидва методи розбивають задачу на менші частини, вони роблять це принципово по-різному.

##### 1. Жадібний алгоритм (Algorytm Zachłanny)

**Основна ідея:** На кожному кроці робити вибір, який здається **найкращим у даний момент** (локально оптимальним), сподіваючись, що послідовність таких виборів приведе до глобально оптимального рішення.

**Як це працює:**

1. Розглядається поточний стан задачі.
2. Робиться вибір, який є найкращим згідно з певним "жадібним" критерієм (наприклад, взяти найлегший предмет, обрати найкоротший шлях до наступної точки).
3. Цей вибір є **остаточним** і ніколи не переглядається.
4. Процес повторюється, доки задача не буде розв'язана.

**Характеристики:**

- **Простий та швидкий:** Легко реалізувати, зазвичай має низьку часову складність.
- **Не завжди оптимальний:** Для багатьох задач жадібний підхід не гарантує знаходження найкращого глобального рішення. Він може "застрягти" в локальному оптимумі.
- **Ефективний для певних задач:** Для деяких задач (наприклад, задача про вибір заявок, алгоритм Дейкстри, алгоритм Краскала, кодування Хаффмана) жадібний підхід *завжди* дає правильне, оптимальне рішення.

**Аналогія:** Сходження на найвищу гору в гірському хребті, завжди обираючи найкрутіший підйом. Ви можете швидко дістатися до вершини пагорба, але пропустити найвищу гору, яка була поруч.

##### 2. Динамічне програмування (Programowanie Dynamiczne)

**Основна ідея:** Розбити складну задачу на **підзадачі, що перекриваються (overlapping subproblems)**, розв'язати кожну унікальну підзадачу лише один раз, зберегти її результат і використовувати ці збережені результати для розв'язання більших підзадач, аж до початкової.

**Як це працює:**

1. Задача розбивається на менші підзадачі.
2. Розв'язуються найпростіші (базові) підзадачі.
3. Їхні результати зберігаються (в таблиці або масиві — цей процес називається **мемоізація** або **табуляція**).
4. Результати менших підзадач комбінуються для розв'язання складніших підзадач.
5. Процес продовжується, доки не буде знайдено рішення для початкової задачі.

**Характеристики:**

- **Гарантує оптимальне рішення:** Оскільки розглядаються всі можливі варіанти на рівні підзадач, динамічне програмування завжди знаходить глобальний оптимум.
- **Складніший та повільніший:** Зазвичай вимагає більше пам'яті (для зберігання результатів) і може мати вищу часову складність, ніж жадібний підхід.
- **Використовується для задач з властивостями:**
  - **Оптимальна підструктура:** Оптимальне рішення всієї задачі може бути побудоване з оптимальних рішень її підзадач.
  - **Підзадачі, що перекриваються:** Одні й ті самі підзадачі зустрічаються багато разів у процесі рекурсивного розв'язання.

**Аналогія:** Пошук найкоротшого шляху в лабіринті шляхом систематичного обчислення та запису найкоротшого шляху до кожної клітинки лабіринту, починаючи від старту.

##### 3. Ключові відмінності: Таблиця порівняння

| Характеристика | Жадібний алгоритм | Динамічне програмування |
|:---|:---|:---|
| **Принцип вибору** | Робить локально оптимальний вибір. | Робить вибір на основі розв'язків підзадач. |
| **Гарантія оптимуму** | **Не завжди.** Тільки для специфічних задач. | **Завжди.** |
| **Погляд на майбутнє** | "Короткозорий", не дивиться наперед. | Враховує майбутні кроки через розв'язки підзадач. |
| **Перегляд рішень** | Рішення є остаточним і не переглядається. | Може "переглядати" рішення, обираючи кращий варіант серед розв'язків підзадач. |
| **Підзадачі** | Не розв'язує підзадачі повторно; просто зменшує задачу на кожному кроці. | Розв'язує підзадачі, що перекриваються, і зберігає їхні результати. |
| **Складність** | Зазвичай простіший і швидший. | Зазвичай складніший і потребує більше ресурсів (часу та пам'яті). |
| **Приклад задачі** | Задача про здачу решти (для канонічних систем монет). | Задача про рюкзак (0/1 Knapsack Problem). |

**Приклад з життя:**

- **Жадібний підхід:** Щоб дістатися з точки А в точку Б, на кожному перехресті ви обираєте дорогу, яка виглядає найкоротшою або найшвидшою в даний момент.
- **Динамічний підхід:** Ви використовуєте навігатор (наприклад, Google Maps), який вже прорахував усі можливі маршрути та їхні підсегменти, щоб знайти гарантовано найкращий шлях.

---

#### Po polsku (PL)

**Algorytmy zachłanne** i **programowanie dynamiczne** to dwa podejścia do rozwiązywania problemów optymalizacyjnych. Chociaż obie metody dzielą problem na mniejsze części, robią to w fundamentalnie różny sposób.

##### 1. Algorytm zachłanny

**Główna idea:** Na każdym kroku dokonywać wyboru, który wydaje się **najlepszy w danym momencie** (lokalnie optymalny), mając nadzieję, że sekwencja takich wyborów doprowadzi do globalnie optymalnego rozwiązania.

**Jak to działa:**

1. Rozpatrywany jest bieżący stan problemu.
2. Dokonywany jest wybór, który jest najlepszy według pewnego "zachłannego" kryterium (np. wziąć najlżejszy przedmiot, wybrać najkrótszą ścieżkę do następnego punktu).
3. Ten wybór jest **ostateczny** i nigdy nie jest przeglądany ponownie.
4. Proces powtarza się, aż problem zostanie rozwiązany.

**Charakterystyka:**

- **Prosty i szybki:** Łatwy w implementacji, zazwyczaj ma niską złożoność czasową.
- **Nie zawsze optymalny:** Dla wielu problemów podejście zachłanne nie gwarantuje znalezienia najlepszego globalnego rozwiązania. Może "utknąć" w lokalnym optimum.
- **Efektywny dla pewnych problemów:** Dla niektórych problemów (np. problem wyboru zadań, algorytm Dijkstry, algorytm Kruskala, kodowanie Huffmana) podejście zachłanne *zawsze* daje poprawne, optymalne rozwiązanie.

**Analogia:** Wspinaczka na najwyższą górę w paśmie górskim, zawsze wybierając najstromsze podejście. Możesz szybko dotrzeć na szczyt pagórka, ale przegapić najwyższą górę, która była obok.

##### 2. Programowanie dynamiczne

**Główna idea:** Podzielić złożony problem na **nakładające się podproblemy (overlapping subproblems)**, rozwiązać każdy unikalny podproblem tylko raz, zapisać jego wynik i wykorzystać te zapisane wyniki do rozwiązywania większych podproblemów, aż do oryginalnego.

**Jak to działa:**

1. Problem dzieli się na mniejsze podproblemy.
2. Rozwiązywane są najprostsze (bazowe) podproblemy.
3. Ich wyniki są zapisywane (w tabeli lub tablicy — proces ten nazywa się **memoizacją** lub **tabulacją**).
4. Wyniki mniejszych podproblemów są łączone w celu rozwiązania bardziej złożonych podproblemów.
5. Proces trwa, aż zostanie znalezione rozwiązanie dla oryginalnego problemu.

**Charakterystyka:**

- **Gwarantuje optymalne rozwiązanie:** Ponieważ rozpatrywane są wszystkie możliwe warianty na poziomie podproblemów, programowanie dynamiczne zawsze znajduje globalne optimum.
- **Bardziej złożone i wolniejsze:** Zazwyczaj wymaga więcej pamięci (do przechowywania wyników) i może mieć wyższą złożoność czasową niż podejście zachłanne.
- **Używane dla problemów z właściwościami:**
  - **Optymalna podstruktura:** Optymalne rozwiązanie całego problemu można zbudować z optymalnych rozwiązań jego podproblemów.
  - **Nakładające się podproblemy:** Te same podproblemy pojawiają się wiele razy w procesie rekurencyjnego rozwiązywania.

**Analogia:** Szukanie najkrótszej ścieżki w labiryncie poprzez systematyczne obliczanie i zapisywanie najkrótszej ścieżki do każdej komórki labiryntu, zaczynając od startu.

##### 3. Kluczowe różnice: Tabela porównawcza

| Cecha | Algorytm zachłanny | Programowanie dynamiczne |
|:---|:---|:---|
| **Zasada wyboru** | Dokonuje lokalnie optymalnego wyboru. | Dokonuje wyboru na podstawie rozwiązań podproblemów. |
| **Gwarancja optimum** | **Nie zawsze.** Tylko dla specyficznych problemów. | **Zawsze.** |
| **Spojrzenie w przyszłość** | "Krótkowzroczny", nie patrzy do przodu. | Uwzględnia przyszłe kroki poprzez rozwiązania podproblemów. |
| **Przegląd decyzji** | Decyzja jest ostateczna i nie jest przeglądana. | Może "przeglądać" decyzje, wybierając lepszy wariant spośród rozwiązań podproblemów. |
| **Podproblemy** | Nie rozwiązuje podproblemów ponownie; po prostu zmniejsza problem w każdym kroku. | Rozwiązuje nakładające się podproblemy i zapisuje ich wyniki. |
| **Złożoność** | Zazwyczaj prostszy i szybszy. | Zazwyczaj bardziej złożony i wymaga więcej zasobów (czasu i pamięci). |
| **Przykład problemu** | Problem wydawania reszty (dla kanonicznych systemów monet). | Problem plecakowy (0/1 Knapsack Problem). |

**Przykład z życia:**

- **Podejście zachłanne:** Aby dotrzeć z punktu A do punktu B, na każdym skrzyżowaniu wybierasz drogę, która wydaje się najkrótsza lub najszybsza w danym momencie.
- **Podejście dynamiczne:** Używasz nawigacji (np. Google Maps), która już przeliczyła wszystkie możliwe trasy i ich podsegmenty, aby znaleźć gwarantowanie najlepszą ścieżkę.

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

**RU:** Схарактеризуй структуру HTML документа.

**PL:** Scharakteryzuj strukturę dokumentu HTML.

### Обьяснение / Wyjaśnienie

**RU:**

## Структура HTML-документа

**HTML-документ** — это не просто набор текста, а **строгая иерархическая структура (дерево)**, состоящая из элементов, называемых **тегами**. Вложенность тегов и их правильная последовательность называется **DOM (Document Object Model)**.

### Базовый скелет

Любая правильная веб-страница начинается с этого стандартного шаблона:

```html
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <title>Заголовок страницы</title>
</head>
<body>
    <h1>Привет, мир!</h1>
</body>
</html>
```

### Разбор основных элементов

**1. <!DOCTYPE html>**

Это не тег, а инструкция для браузера. Стоит самой первой и указывает на стандарт **HTML5**. Без этой строки браузер отобразит страницу некорректно.

**2. <html>** — корневой элемент

Весь документ находится внутри этих тегов. Атрибут `lang="ru"` важен для поисковиков и скринридеров (программ для чтения с экрана), указывая язык контента.

**3. Два обязательных раздела: <head> и <body>**

Внутри `<html>` документ всегда делится на две части:

**<head> (Голова):**
- Служебная информация (метаданные)
- Не видна пользователю на странице (кроме заголовка во вкладке)
- Здесь подключаются стили (CSS), шрифты, скрипты (JS), указывается кодировка (UTF-8)
- Ключевой тег: `<title>` — название вкладки браузера

**<body> (Тело):**
- Содержит весь видимый контент: текст, картинки, кнопки, видео
- Всё, что видит пользователь, должно быть здесь

### Семантическая структура (HTML5)

В прошлом верстка строилась на одних `<div>`. Современный **HTML5** использует **семантические теги** — специальные разделы, которые объясняют браузеру и поисковикам роль контента:

**<header>** — «шапка» сайта или раздела (логотип, меню)

**<nav>** — блок навигации (ссылки)

**<main>** — основной контент страницы (один на страницу)

**<section>** / **<article>** — смысловые разделы

**<footer>** — «подвал» сайта (копирайты, контакты)

**<h1>–<h6>** — заголовки (от самого важного H1 до наименее важного H6)

### Краткая версия (для собеседования, 40–60 сек)

- **DOM** — древовидная структура HTML-документа.
- **<!DOCTYPE html>** — инструкция для браузера использовать HTML5.
- **<html>** — корневой тег. Внутри два раздела:
  - **<head>** — метаданные, CSS, JS, `<title>` (не видно пользователю)
  - **<body>** — весь видимый контент
- **Семантические теги** (`<header>`, `<main>`, `<footer>`, `<section>`) делают код логичным для SEO и доступности.

**PL:**

## Struktura dokumentu HTML

**Dokument HTML** — to nie tylko tekst, ale **ścisła hierarchiczna struktura (drzewo)** złożona z elementów zwanych **tagami**. Zagnieżdżanie tagów i ich prawidłowa kolejność to **DOM (Document Object Model)**.

### Podstawowy szkielet

Każda prawidłowa strona internetowa zaczyna się od tego standardowego szablonu:

```html
<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <title>Tytuł strony</title>
</head>
<body>
    <h1>Cześć, świecie!</h1>
</body>
</html>
```

### Analiza głównych elementów

**1. <!DOCTYPE html>**

To nie tag, lecz instrukcja dla przeglądarki. Stoi na początku i wskazuje na standard **HTML5**. Bez tej linii przeglądarka wyświetli stronę niepoprawnie.

**2. <html>** — element główny

Cały dokument znajduje się wewnątrz tych tagów. Atrybut `lang="pl"` jest ważny dla wyszukiwarek i czytników ekranu (programów dla osób niewidomych), wskazując język zawartości.

**3. Dwie obowiązkowe sekcje: <head> i <body>**

Wewnątrz `<html>` dokument zawsze dzieli się na dwie części:

**<head> (Nagłówek):**
- Informacje pomocnicze (metadane)
- Nie widoczna dla użytkownika na stronie (oprócz tytułu na karcie)
- Tutaj podłączane są style (CSS), czcionki, skrypty (JS), kodowanie (UTF-8)
- Kluczowy tag: `<title>` — nazwa karty przeglądarki

**<body> (Treść):**
- Zawiera całą widoczną zawartość: tekst, obrazy, przyciski, wideo
- Wszystko, co widzi użytkownik, powinno być tutaj

### Struktura semantyczna (HTML5)

W przeszłości układ budowano na samych `<div>`. Nowoczesny **HTML5** używa **tagów semantycznych** — specjalnych sekcji, które wyjaśniają przeglądarce i wyszukiwarkom rolę zawartości:

**<header>** — «głowica» strony lub sekcji (logo, menu)

**<nav>** — blok nawigacji (linki)

**<main>** — główna zawartość strony (jeden na stronę)

**<section>** / **<article>** — logiczne sekcje

**<footer>** — «stopka» strony (prawa autorskie, kontakt)

**<h1>–<h6>** — nagłówki (od najważniejszego H1 do najmniej ważnego H6)

### Krótka wersja (do nauki, 40–60 s)

- **DOM** — hierarchiczna struktura dokumentu HTML.
- **<!DOCTYPE html>** — instrukcja dla przeglądarki, aby użyć HTML5.
- **<html>** — tag główny. Wewnątrz dwie sekcje:
  - **<head>** — metadane, CSS, JS, `<title>` (niewidoczne dla użytkownika)
  - **<body>** — całą widoczną zawartość
- **Tagi semantyczne** (`<header>`, `<main>`, `<footer>`, `<section>`) czynią kod logicznym dla SEO i dostępności.

---

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

**RU:** Схарактеризуй архитуктуру приложения ориентированную на сервисы. SOA - Service Oriented Architecture.

**PL:** Scharakteryzuj architekturę aplikacji zorientowaną na usługi (ang. Service Oriented Architecture)

### Обьяснение / Wyjaśление

**RU:**

## Архитектура, ориентированная на сервисы (SOA)

**Service-Oriented Architecture (SOA)** — это архитектурный стиль, в котором приложение строится из набора дискретных и слабосвязанных компонентов, называемых **сервисами**.

Каждый сервис реализует определённую бизнес-логику и может взаимодействовать с другими сервисами через сеть. Главная цель SOA — **повторное использование кода** и **лёгкая интеграция** разных систем.

### Сравнение архитектур

На изображении ниже показаны различия в декомпозиции между тремя подходами:

<img src="img/soa_monolit_microservices.png" alt="drawing" width="600"/>

**Монолит:** вся система — это единый неделимый блок; все компоненты жёстко связаны.

**Микросервисы:** логика разбита на максимально мелкие, независимые единицы, каждая отвечает за одну узкую задачу.

**SOA:** занимает место «посередине» — мы разделяем систему на крупные логические модули (бизнес-сервисы), часто объединённые общей шиной данных (ESB).

### Основные принципы SOA

Не существует единого стандарта, но выделяют ключевые принципы манифеста SOA:

**1. Абстрагирование (Service Abstraction)**
Сервис — это «чёрный ящик». Потребителю не нужно знать, как он устроен внутри, на каком языке написан (Java, Python, C#) и какая у него база данных. Важен только контракт взаимодействия.

**2. Слабая связность (Loose Coupling)**
Сервисы должны иметь минимум зависимостей друг от друга. Изменение внутри одного сервиса не должно ломать работу других.

**3. Отсутствие состояния (Statelessness)**
Сервисы не должны хранить информацию о сессии или предыдущих запросах. Каждый запрос должен содержать всю необходимую информацию.

**4. Стандартизация контрактов (Standardized Contracts)**
Каждый сервис имеет описание (контракт), определяющее его функциональность и способ взаимодействия (например, WSDL для SOAP или OpenAPI для REST). Это гарантирует совместимость.


### Компоненты архитектуры

<img src="img/soaARCH.png" alt="drawing" width="600"/>

Классическая SOA состоит из трёх основных ролей и связующего элемента:

**Поставщик сервиса (Service Provider)**
Создаёт, поддерживает и предоставляет сервис. Публикует описание сервиса в реестре.

**Потребитель сервиса (Service Consumer)**
Система или приложение, которое использует функционал. Ищет сервис в реестре и отправляет запрос поставщику.

**Реестр сервисов (Service Registry)**
Справочник («телефонная книга»), где хранятся адреса и описания доступных сервисов. Позволяет потребителям находить поставщиков.

**Enterprise Service Bus (ESB)**
Часто используется «Сервисная Шина Предприятия» — прослойка, управляющая передачей сообщений между сервисами, маршрутизацией и преобразованием форматов данных.

### Краткая версия (для собеседования, 40–60 сек)

- **SOA** — подход, при котором приложение собирается из независимых бизнес-сервисов, взаимодействующих по сети.
- **Отличие от микросервисов:** В SOA сервисы более крупные (бизнес-функции) и используют общую шину данных (ESB), тогда как микросервисы максимально децентрализованы.
- **Принципы:** слабая связность, абстракция, повторное использование, стандартизированные контракты.
- **Компоненты:** Поставщик (создаёт), Потребитель (использует), Реестр (хранит адреса) и ESB (маршрутизирует).

**PL:**

## Architektura zorientowana na usługi (SOA)

**Service-Oriented Architecture (SOA)** — to styl architektoniczny, w którym aplikacja budowana jest z zestawu dyskretnych i słabo powiązanych komponentów, zwanych **usługami**.

Każda usługa realizuje określoną logikę biznesową i może komunikować się z innymi usługami przez sieć. Głównym celem SOA jest **ponowne użycie kodu** i **łatwa integracja** różnych systemów.

### Porównanie architektur

Na poniższym obrazie przedstawiono różnice w dekompozycji między trzema podejściami:

<img src="img/soa_monolit_microservices" alt="drawing" width="600"/>

**Monolity:** cały system to jeden niepodzielny blok; wszystkie komponenty są ściśle powiązane.

**Mikroserwisy:** logika podzielona na maksymalnie małe, niezależne jednostki, każda odpowiada za jedno wąskie zadanie.

**SOA:** zajmuje miejsce „pośrodku" — dzielimy system na duże moduły logiczne (usługi biznesowe), często połączone wspólną szyną danych (ESB).

### Główne zasady SOA

Nie ma jednego standardu, ale wyróżnia się kluczowe zasady manifestu SOA:

**1. Abstrakcja (Service Abstraction)**
Usługa to «czarna skrzynka». Konsument nie musi wiedzieć, jak jest zbudowana, w jakim języku (Java, Python, C#) czy jaką ma bazę danych. Ważny jest tylko kontrakt interakcji.

**2. Luźne powiązanie (Loose Coupling)**
Usługi powinny mieć minimum zależności od siebie. Zmiana wewnątrz jednej usługi nie powinna psować pracy innych.

**3. Brak stanu (Statelessness)**
Usługi nie powinny przechowywać informacji o sesji lub poprzednich żądaniach. Każde żądanie musi zawierać wszystkie niezbędne informacje.

**4. Standaryzacja kontraktów (Standardized Contracts)**
Każda usługa ma opis (kontrakt), określający jej funkcjonalność i sposób komunikacji (np. WSDL dla SOAP lub OpenAPI dla REST). Gwarantuje to kompatybilność.

### Komponenty architektury

<img src="img/soaARCH.png" alt="drawing" width="600"/>

Klasyczna SOA składa się z trzech głównych ról i elementu łączącego:

**Dostawca usługi (Service Provider)**
Tworzy, utrzymuje i udostępnia usługę. Publikuje opis usługi w rejestrze.

**Konsument usługi (Service Consumer)**
System lub aplikacja, która wykorzystuje funkcjonalność. Szuka usługi w rejestrze i wysyła żądanie dostawcy.

**Rejestr usług (Service Registry)**
Katalog («księga adresowa»), gdzie przechowywane są adresy i opisy dostępnych usług. Umożliwia konsumentom znalezienie dostawców.

**Enterprise Service Bus (ESB)**
Często używana «Magistrala Usług Przedsiębiorstwa» — warstwa, która zarządza transmisją wiadomości między usługami, routingiem i transformacją formatów danych.

### Krótka wersja (do nauki, 40–60 s)

- **SOA** — podejście, w którym aplikacja składa się z niezależnych usług biznesowych komunikujących się przez sieć.
- **Różnica od mikroserwisów:** W SOA usługi są większe (funkcje biznesowe) i używają wspólnej magistrali danych (ESB), podczas gdy mikroserwisy są maksymalnie zdecentralizowane.
- **Zasady:** luźne powiązanie, abstrakcja, ponowne użycie, standaryzowane kontrakty.
- **Komponenty:** Dostawca (tworzy), Konsument (używa), Rejestr (przechowuje adresy) i ESB (routuje).

---

## Питання 31 / Pytanie 31

**RU:** Функциональные интерфейсы и лямблда выражения в языке Java. Оговори и подай пример.

**PL:** Interfejsy funkcyjne i wyrażenia lambda w języku Java. Omów i podaj przykłady.

### Обьяснение / Wyjaśление

**RU:**

## Функциональные интерфейсы и Лямбда-выражения (Java 8)

С выходом Java 8 язык сделал большой шаг в сторону функционального программирования. Это позволило писать код короче и выразительнее, передавая поведение как аргументы.

### 1. Функциональный интерфейс

Это интерфейс, который содержит **ровно один абстрактный метод** (при этом может содержать любое количество методов `default` или `static`).

**Аннотация @FunctionalInterface:** помечает интерфейс. Она не обязательна, но полезна — компилятор выдаст ошибку, если вы добавите второй абстрактный метод, нарушив правило.

**Примеры встроенных функциональных интерфейсов:**
- `Runnable` — без параметров, нет возврата
- `Callable<V>` — без параметров, возвращает V
- `Comparator<T>` — сравнение двух объектов
- Из пакета `java.util.function`: `Predicate<T>`, `Consumer<T>`, `Function<T, R>`, `Supplier<T>`

### 2. Лямбда-выражения (Lambda Expressions)

Лямбда — это компактная запись анонимной функции (реализации функционального интерфейса). Она позволяет избежать громоздкого синтаксиса анонимных классов.

**Структура лямбды состоит из трех частей:**

1. **Аргументы:** `(x, y)` — параметры метода
2. **Оператор стрелка:** `->` — разделяет параметры и тело функции
3. **Тело:** выражение или блок кода, который выполняется

### Синтаксис и правила

Лямбды записываются по-разному в зависимости от сложности логики:

**А) Однострочное выражение (Expression style)**

Если действие занимает одну строку, фигурные скобки и `return` не требуются — Java автоматически вернет результат.

```java
(a) -> a > 0   // Возвращает true, если a > 0
```

**Б) Блок кода (Block style)**

Для сложной логики требуются фигурные скобки и явный `return`.

```java
(a) -> {
    System.out.println("Checking...");
    return a > 0;
}
```

**В) Упрощение аргументов**

При одном аргументе скобки можно опустить; при нескольких или при их отсутствии — скобки обязательны.

```java
a -> a * 2        // Один аргумент
() -> "Hello"     // Нет аргументов
(x, y) -> x + y   // Несколько аргументов
```

### Пример: Эволюция кода

**До Java 8 (Анонимный класс):**

```java
// Сортировка списка строк по длине
Collections.sort(names, new Comparator<String>() {
    @Override
    public int compare(String a, String b) {
        return a.length() - b.length();
    }
});
```

**С Java 8 (Лямбда):**

```java
// То же самое — одна строка
Collections.sort(names, (a, b) -> a.length() - b.length());
```

##### Краткая версия (для собеседования, 40–60 сек)

- **Функциональный интерфейс** - это интерфейс, который имеет только один абстрактный метод. Может помечаться аннотацией @FunctionalInterface для контроля компилятором.
- **Лямбда-выражение** - это краткая реализация такого интерфейса (анонимная функция). Позволяет писать код в функциональном стиле.
- **Синтаксис** - Состоит из трех частей: аргументы (), стрелка -> и тело метода.
- **Особенность** - Если тело состоит из одной строки, return и фигурные скобки {} не нужны (это называется expression body). Если строк несколько — скобки и return обязательны.

**PL:**

## Interfejsy funkcyjne i wyrażenia lambda (Java 8)

Z pojawieniam się Java 8 język zrobił duży krok w kierunku programowania funkcjonalnego. To pozwoliło na pisanie kodu bardziej zwięzłego i wyrażającego, przekazując zachowanie jako argumenty.

### 1. Interfejs funkcyjny

To interfejs, który zawiera **dokładnie jedną metodę abstrakcyjną** (może zawierać dowolną liczbę metod `default` lub `static`).

**Adnotacja @FunctionalInterface:** oznacza interfejs. Nie jest obowiązkowa, ale jest przydatna — kompilator wyda błąd, jeśli dodasz drugą metodę abstrakcyjną, naruszając zasadę.

**Przykłady wbudowanych interfejsów funkcyjnych:**
- `Runnable` — bez parametrów, brak zwrotu
- `Callable<V>` — bez parametrów, zwraca V
- `Comparator<T>` — porównanie dwóch obiektów
- Z pakietu `java.util.function`: `Predicate<T>`, `Consumer<T>`, `Function<T, R>`, `Supplier<T>`

### 2. Wyrażenia lambda (Lambda Expressions)

Lambda to kompaktowy zapis funkcji anonimowej (implementacji interfejsu funkcyjnego). Pozwala uniknąć skomplikowanej składni klas anonimowych.

**Struktura lambdy składa się z trzech części:**

1. **Argumenty:** `(x, y)` — parametry metody
2. **Operator strzałka:** `->` — oddziela parametry od ciała funkcji
3. **Ciało:** wyrażenie lub blok kodu, który się wykonuje

### Składnia i reguły

Lambdy zapisuje się na różne sposoby w zależności od złożoności logiki:

**A) Jednowierszowe wyrażenie (Expression style)**

Jeśli działanie zajmuje jeden wiersz, nawiasy klamrowe i `return` nie są wymagane — Java automatycznie zwróci wynik.

```java
(a) -> a > 0   // Zwraca true, jeśli a > 0
```

**B) Blok kodu (Block style)**

Dla złożonej logiki wymagane są nawiasy klamrowe i jawny `return`.

```java
(a) -> {
    System.out.println("Checking...");
    return a > 0;
}
```

**C) Uproszczenie argumentów**

Przy jednym argumencie nawiasy można opuścić; przy kilku lub braku argumentów — nawiasy są obowiązkowe.

```java
a -> a * 2        // Jeden argument
() -> "Hello"     // Brak argumentów
(x, y) -> x + y   // Kilka argumentów
```

### Przykład: Ewolucja kodu

**Przed Java 8 (Klasa anonimowa):**

```java
// Sortowanie listy ciągów znaków po długości
Collections.sort(names, new Comparator<String>() {
    @Override
    public int compare(String a, String b) {
        return a.length() - b.length();
    }
});
```

**Z Java 8 (Lambda):**

```java
// To samo — jeden wiersz
Collections.sort(names, (a, b) -> a.length() - b.length());
```

##### Krótka wersja (do nauki, 40–60 s)

- **Interfejs funkcyjny** — to interfejs z dokładnie jedną metodą abstrakcyjną. Może być oznaczony adnotacją @FunctionalInterface dla kontroli kompilatora.
- **Wyrażenie lambda** — to zwięzła implementacja takiego interfejsu (funkcja anonimowa). Pozwala pisać kod w stylu funkcjonalnym.
- **Składnia** — składa się z trzech części: argumenty (), strzałka -> i ciało metody.
- **Szczególność** — jeśli ciało zawiera jeden wiersz, `return` i nawiasy klamrowe {} nie są potrzebne (zwane expression body). Jeśli wierszy jest więcej — nawiasy i return są obowiązkowe.

---

## Питання 32 / Pytanie 32

**RU:** На выбранном примере оговорить проблему (?) Stream API в языке Java.

**PL:** Na wybranym przykładzie omów zagadnienie strumieni w języku Java.

### Пояснення / Wyjaśление

**RU:**
**Stream API** появилось в Java 8 и кардинально изменило подход к написанию кода. Это ознаменовало переход от **императивного стиля** (циклы for, if) к **функциональному**.

Основная идея: мы больше не пишем, *как* итерировать коллекцию, мы пишем, *что* мы хотим с ней сделать.

**Диаграмма:**
<img src="img/JavaStreamAPI.png" alt="drawing" width="600"/>

**Как это работает**

Работу со стримами можно представить как конвейер. Обычно процесс состоит из трех этапов:

1. **Создание (Input)**
    * Входная точка. Чаще всего создается из коллекции: `list.stream()`.

2. **Обработка (Intermediate Operations)**
    * Настройка конвейера (фильтрация, преобразование).

3. **Завершение (Terminal Operation)**
    * Запуск конвейера и получение результата.

**Важные особенности**

* **Одноразовость**: Стрим (Поток) можно использовать только один раз. После вызова терминальной операции он закрывается. Если попытаться вызвать метод повторно — упадет исключение.

* **Ленивость (Lazy Evaluation)**: Промежуточные операции не выполняются, пока не будет вызвана терминальная операция. Стрим просто «запоминает» набор команд, но данные не текут, пока не потребуют результат.

**Типы операций**

1. **Промежуточные (Intermediate)**
    * Возвращают новый Stream. Их можно объединять в цепочки.
    * `.filter(Predicate)` — фильтрует поток, оставляя только элементы, соответствующие условию (возвращающие true).
    * `.map(Function)` — преобразует каждый элемент в другой объект (например, из User достает String name).
    * `.sorted()` — сортирует элементы.
    * `.distinct()` — убирает дубликаты.

2. **Терминальные (Terminal)**
    * Запускают выполнение потока и возвращают результат (или void), но не Stream. После этого стрим умирает.
    * `.collect(Collectors.toList())` — собрать результат обратно в List/Set/Map.
    * `.forEach(Consumer)` — выполнить действие для каждого элемента (например, вывод в консоль).
    * `.count()` — вернуть количество элементов.
    * `.findFirst()` — вернуть первый элемент (обернутый в Optional).

##### Краткая версия (для собеседования, 40–60 сек)

- **Stream API** (Java 8) — инструмент для обработки данных в функциональном стиле.
- **Суть**: Говорим четкие инструкции что сделать.
- **Жизненный цикл**: Создание (collection.stream()) → промежуточные операции (filter, map, sorted, distinct) → терминальная операция (collect, forEach, count).
- **Ключевые свойства**: Ленивость (промежуточные операции не выполняются до вызова терминальной); одноразовость (стрим умирает после терминальной операции).

---

**PL:**
**Stream API** pojawiło się w Java 8 i zasadniczo zmieniło podejście do pisania kodu. Oznaczało to przejście od **stylu imperatywnego** (pętle for, if) do **funkcjonalnego**.

Podstawowa idea: zamiast pisać, *jak* iterować kolekcję, piszemy, *co* chcemy z nią zrobić.

**Diagram:**
<img src="img/JavaStreamAPI.png" alt="drawing" width="600"/>

**Jak to działa (Pipeline)**

Pracę ze strumieniami można przedstawić jako konwejor. Proces zwykle obejmuje trzy etapy:

1. **Tworzenie (Source)**
    * Punkt wejścia. Najczęściej tworzone z kolekcji: `list.stream()`.

2. **Przetwarzanie (Intermediate Operations)**
    * Konfiguracja konwejera (filtrowanie, transformacja).

3. **Zakończenie (Terminal Operation)**
    * Uruchomienie konwejera i uzyskanie wyniku.

**Ważne cechy**

* **Jednorazowość**: Strumień można użyć tylko raz. Po wywołaniu operacji terminalnej strumień zostaje zamknięty. Próba ponownego wywołania metody spowoduje wyjątek.

* **Leniwość (Lazy Evaluation)**: Operacje pośrednie nie są wykonywane, dopóki nie zostanie wywołana operacja terminalna. Strumień po prostu „zapamiętuje" zestaw poleceń, ale dane nie płyną, dopóki nie żądasz wyniku.

**Typy operacji**

1. **Pośrednie (Intermediate)**
    * Zwracają nowy Stream. Można je łączyć w łańcuchy.
    * `.filter(Predicate)` — filtruje strumień, pozostawiając tylko elementy spełniające warunek (zwracające true).
    * `.map(Function)` — transformuje każdy element na inny obiekt (np. z User wyciąga String name).
    * `.sorted()` — sortuje elementy.
    * `.distinct()` — usuwa duplikaty.

2. **Terminalne (Terminal)**
    * Uruchamiają wykonanie strumienia i zwracają wynik (lub void), ale nie Stream. Potem strumień umiera.
    * `.collect(Collectors.toList())` — zbierz wynik z powrotem w List/Set/Map.
    * `.forEach(Consumer)` — wykonaj akcję dla każdego elementu (np. wydruk na konsolę).
    * `.count()` — zwróć liczbę elementów.
    * `.findFirst()` — zwróć pierwszy element (owinięty w Optional).

##### Wersja krótka (do nauki, 40–60 s)

- **Stream API** (Java 8) — narzędzie do przetwarzania danych w stylu funkcjonalnym.
- **Istota**: Pozwala pisać kod deklaratywny (opisujemy «co», a nie «jak»).
- **Cykl życia**: Tworzenie (collection.stream()) → operacje pośrednie (filter, map, sorted, distinct) → operacja terminalna (collect, forEach, count).
- **Kluczowe właściwości**: Leniwość (operacje pośrednie nie wykonują się do wywołania operacji terminalnej); jednorazowość (strumień umiera po operacji terminalnej).

---

## Питання 33 / Pytanie 33

**RU:** Коллекции в Java. Оговори и подай пример их использования.

**PL:** Kolekcje w języku Java. Omów i podaj przykłady ich zastosowania.
### Пояснення / Wyjaśnienie

**RU:**
**Java Collection Framework** — это единая архитектура для представления и манипулирования коллекциями объектов. Она предоставляет стандартные интерфейсы и их реализации.

Глобально в Java есть две отдельные ветки иерархии:
- **Collection** (наследники Iterable) — работа с одиночными элементами
- **Map** — работа с парами «Ключ-Значение»

Начнем с ветки Collection:

1. **Iterable и Collection**
    * **Iterable**: Корневой интерфейс. Гарантирует, что объект можно перебрать в цикле for-each.
    * **Collection**: Основной интерфейс для всех коллекций (кроме Map). Методы: `add()`, `remove()`, `size()`, `contains()`.

2. **List** (Списки)
    * Суть: Упорядоченная коллекция, допускающая дубликаты. Каждый элемент имеет индекс (как в массиве).
    * **ArrayList**
        - Динамический массив с автоматическим расширением.
        - Плюсы: Быстрый доступ по индексу ($O(1)$).
        - Минусы: Медленная вставка/удаление в середину (требуется сдвиг элементов).
        - Когда использовать: В 90% случаев для простого хранения и чтения.
    * **LinkedList**
        - Двусвязный список. Каждый элемент хранит ссылку на предыдущий и следующий.
        - Плюсы: Быстрая вставка/удаление в начало или середину ($O(1)$ при наличии итератора).
        - Минусы: Медленный доступ по индексу ($O(n)$) — нужно перебирать элементы.
        - Когда использовать: Если коллекция часто модифицируется в середине, но редко читается по индексу.

3. **Queue и Deque** (Очереди)
    * Суть: Коллекции для хранения элементов в порядке обработки (обычно FIFO — First In, First Out).
    * **Queue**
        - `PriorityQueue`: Упорядоченная очередь. Элементы выходят согласно приоритету, а не порядку вставки.
    * **Deque** (Double Ended Queue)
        - Двусторонняя очередь. Можно добавлять и забирать элементы с обоих концов.
        - `ArrayDeque`: Более быстрая альтернатива классу Stack.

4. **Set** (Множества)
    * Суть: Коллекция уникальных элементов. Дубликаты не сохраняются.
    * **HashSet**
        - Самая популярная реализация. Использует HashMap внутри.
        - Порядок элементов не гарантируется.
        - Очень быстрые операции добавления и поиска ($O(1)$) благодаря хешированию.
    * **LinkedHashSet**
        - Запоминает порядок добавления элементов.
        - Чуть медленнее, чем HashSet.
    * **TreeSet**
        - Хранит элементы в отсортированном виде (Red-Black Tree).
        - Вставка медленнее ($O(\log n)$), но идеально для упорядоченных уникальных данных.

5. **Map** (Словари)
    * Суть: Хранит пары Ключ → Значение. Работает отдельно от интерфейса Collection.
    * Ключи должны быть уникальны.
    * **HashMap**
        - Самое популярное решение.
        - Вычисляет `hashCode` ключа, определяет "корзину" (bucket) и кладет туда значение.
        - **Важно**: Критически зависит от правильной реализации `equals()` и `hashCode()` у объекта-ключа. Плохая хеш-функция снижает производительность до уровня связного списка.
        - Плюсы: Мгновенный доступ по ключу при отсутствии коллизий.
    * **TreeMap**
        - Ключи хранятся в отсортированном порядке.
    * **LinkedHashMap**
        - Хранит порядок добавления ключей.

**Диаграмма:**
<img src="img/CollectionsJava.png" alt="drawing" width="600"/>

##### Краткая версия

- **Две основные ветки**: Collection (одиночные элементы) и Map (пары Ключ-Значение).
- **List**: Упорядоченные списки. ArrayList — массив (быстрое чтение по индексу $O(1)$), LinkedList — связный список (быстрая вставка/удаление).
- **Set**: Уникальные элементы. HashSet — самый быстрый ($O(1)$), но без гарантии порядка; TreeSet — хранит отсортированными ($O(\log n)$).
- **Queue/Deque**: Очереди (FIFO/LIFO). PriorityQueue выдает элементы по приоритету; ArrayDeque — быстрая двусторонняя очередь.
- **Map**: HashMap — стандартное решение на хешировании (критичны `equals()` и `hashCode()`); TreeMap — для отсортированных ключей.

---

**PL:**
**Java Collection Framework** — to zunifikowana architektura do reprezentacji i manipulacji kolekcjami obiektów. Dostarcza standardowych interfejsów i ich implementacji.

Globalnie w Java istnieją dwie oddzielne gałęzie hierarchii:
- **Collection** (dziedziczące Iterable) — praca z poszczególnymi elementami
- **Map** — praca z parami „Klucz-Wartość"

Zaczniemy od gałęzi Collection:

1. **Iterable i Collection**
    * **Iterable**: Główny interfejs. Gwarancja, że obiekt można iterować w pętli for-each.
    * **Collection**: Podstawowy interfejs dla wszystkich kolekcji (oprócz Map). Metody: `add()`, `remove()`, `size()`, `contains()`.

2. **List** (Listy)
    * Istota: Uporządkowana kolekcja, dopuszczająca duplikaty. Każdy element ma indeks (jak w tablicy).
    * **ArrayList**
        - Dynamiczna tablica z automatycznym rozszerzaniem.
        - Plusy: Szybki dostęp po indeksie ($O(1)$).
        - Minusy: Wolna wstawka/usunięcie w środek (wymagane przesunięcie elementów).
        - Kiedy używać: W 90% przypadków dla zwykłego przechowywania i czytania.
    * **LinkedList**
        - Dwukierunkowa lista powiązana. Każdy element przechowuje referencję do poprzedniego i następnego.
        - Plusy: Szybka wstawka/usunięcie na początek lub środek ($O(1)$ przy iteratorze).
        - Minusy: Wolny dostęp po indeksie ($O(n)$) — trzeba iterować elementy.
        - Kiedy używać: Jeśli kolekcja jest często modyfikowana w środku, ale rzadko czytana po indeksie.

3. **Queue i Deque** (Kolejki)
    * Istota: Kolekcje do przechowywania elementów w porządku przetwarzania (zwykle FIFO — First In, First Out).
    * **Queue**
        - `PriorityQueue`: Uporządkowana kolejka. Elementy wychodzą zgodnie z priorytetem, a nie kolejnością wstawienia.
    * **Deque** (Double Ended Queue)
        - Dwukierunkowa kolejka. Można dodawać i zabierać elementy z obu końców.
        - `ArrayDeque`: Szybsza alternatywa dla klasy Stack.

4. **Set** (Zbiory)
    * Istota: Kolekcja unikalnych elementów. Duplikaty nie są przechowywane.
    * **HashSet**
        - Najpopularniejsza implementacja. Używa HashMap wewnętrznie.
        - Porządek elementów nie jest gwarantowany.
        - Bardzo szybkie operacje dodania i wyszukania ($O(1)$) dzięki haszowaniu.
    * **LinkedHashSet**
        - Pamięta porządek dodania elementów.
        - Nieco wolniejszy niż HashSet.
    * **TreeSet**
        - Przechowuje elementy w posortowanej kolejności (Red-Black Tree).
        - Wstawka wolniejsza ($O(\log n)$), ale idealna dla posortowanych unikalnych danych.

5. **Map** (Słowniki)
    * Istota: Przechowuje pary Klucz → Wartość. Działa niezależnie od interfejsu Collection.
    * Klucze muszą być unikalne.
    * **HashMap**
        - Najpopularniejsze rozwiązanie.
        - Oblicza `hashCode` klucza, określa „koszyk" (bucket) i umieszcza tam wartość.
        - **Ważne**: Krytycznie zależy od prawidłowej implementacji `equals()` i `hashCode()` w obiekcie klucza. Zła funkcja haszująca obniża wydajność do poziomu listy powiązanej.
        - Plusy: Natychmiastowy dostęp po kluczu przy braku kolizji.
    * **TreeMap**
        - Klucze przechowywane w posortowanej kolejności.
    * **LinkedHashMap**
        - Przechowuje porządek dodania kluczy.

**Diagram:**
<img src="img/CollectionsJava.png" alt="drawing" width="600"/>

##### Wersja krótka (do nauki, 40–60 s)

- **Dwie główne gałęzie**: Collection (poszczególne elementy) i Map (pary Klucz-Wartość).
- **List**: Uporządkowane listy. ArrayList — tablica (szybkie czytanie po indeksie $O(1)$), LinkedList — lista powiązana (szybka wstawka/usunięcie).
- **Set**: Unikalne elementy. HashSet — najszybszy ($O(1)$), ale bez gwarancji porządku; TreeSet — przechowuje posortowane ($O(\log n)$).
- **Queue/Deque**: Kolejki (FIFO/LIFO). PriorityQueue zwraca elementy po priorytecie; ArrayDeque — szybka dwukierunkowa kolejka.
- **Map**: HashMap — standardowe rozwiązanie na haszowaniu (krytyczne `equals()` i `hashCode()`); TreeMap — dla posortowanych kluczy.