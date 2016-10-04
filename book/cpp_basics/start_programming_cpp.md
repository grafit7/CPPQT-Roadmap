# Починаємо програмувати

Отже, що ми можемо зробити для початку? Давайте почнемо з того, що напишемо програму, яка виводить якесь повідомлення.

Візьмемо попредню програму та допишемо до неї кілька рядків:

```cpp
#include <iostream>

int main()
{
    std::cout << "I am a hacker!";
}
```

У першому рядку ми підключили бібліотеку `iostream`. Бібліотеки містять у собі набір корисних та готових до використання функцій, типів даних, тощо. iostream містить засоби для вводу\виводу \(і в консоль теж\), які нам необхідна для того щоб вивести повідомлення.

У тілі функції main ми виводимо повідомлення:

* `std::cout` - це стандартний потік виводу, тобто місце, куди програма виводить свої повідомлення \(у нашому випадку це консоль\)

* `"I am a hacker!"` - повідомлення яке ми виводимо. Усі текстові рядки в мові С++ пишуться у подвійних лапках.

* `<<` - оператор \(тобто дія яку ми виконуємо\) - у цьому випадку ми кажемо "вивести!". Щоб зрозуміти, що таке оператор, це можна порівняти, наприклад, з додаванням двох чисел. `2 + 2` означає: до першої двійки додай другу. Тут `+` теж оператор. Тільки у нашому пракладі замість чисел - стандартний потік виводу та рядок тексту, а замість оператора `+` - це оператор `<<` \(який означає "вивести"\).

Не забудьте крапку з комою у кінці! Крапку з комою ставлять після інструкції \(statement\) \(дуже грубо кажучи: інструкція - фрагмент програми який щось виконує щось конкретне\) та виразу \(expression\) \(що містить оператор\). Таким чином крапку з комою використовують для їх розділення у програмі.

> **Деталі: простір імен std**
> 
>  
> 
> ```cpp
> #include <iostream>
> 
> using namespace std;
> 
> int main()
> {
>     cout << "I am a hacker!";
> }
> ```



Аналогічно, ми можемо попросити користувача щось ввести у консолі. Напишемо програму, яка питає ім'я, а потім вітається з користувачем:

```cpp 
#include <iostream>
#include <string>

int main()
{
    std::cout << "Please, enter your name:" << std::endl;
 
    std::string name;
    std::cin >> name;

    std::cout << "Hello, " << name << "!" << std::endl;
}
```
