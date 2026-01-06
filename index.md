# Підготовка до екзамену / Przygotowanie do egzaminu

Цей документ містить питання до екзамену та пояснення до них двома мовами: українською та польською.
Niniejszy dokument zawiera pytania egzaminacyjne wraz z wyjaśnieniami w dwóch językach: ukraińskim i polskim.

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

## Питання 2

**UA:** Які можна виділити моделі процесу створення програмного забезпечення? Охарактеризуйте деякі з них.

**PL:** Jakie można wyróżnić modele procesu tworzenia oprogramowania. Scharakteryzuj niektóre z nich.

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

## Питання 3

**UA:** [Текст питання українською мовою]

**PL:** Jakie są najprostsze algorytmy generacji liczb losowych z zadanym rozkładem prawdopodobieństwa?

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
