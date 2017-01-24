---
title: "Оператор break (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "break_cpp"
  - "break"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "break - ключевое слово [C++]"
ms.assetid: 63739928-8985-4b05-93ce-016322e6da3d
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор break (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Оператор `break` завершает выполнение ближайшего внешнего цикла или условного оператора, в котором он находится.  Управление передается оператору, который расположен после оператора, при его наличии.  
  
## Синтаксис  
  
```  
break;  
```  
  
## Заметки  
 Оператор `break` используется с условным оператором [switch](../cpp/switch-statement-cpp.md) и операторами циклов [do](../cpp/do-while-statement-cpp.md), [for](../cpp/for-statement-cpp.md) и [while](../cpp/while-statement-cpp.md).  
  
 В операторе `switch` оператор `break` заставляет программу выполнять следующий оператор, находящийся снаружи оператора `switch`.  Без оператора `break` выполняется каждый оператор из сопоставленной метки `case` до конца оператора `switch`, включая предложение `default`.  
  
 В циклах оператор `break` завершает выполнение ближайшего внешнего оператора `do`, `for` или `while`.  Управление передается оператору, который расположен после завершенного оператора, при его наличии.  
  
 Если используются вложенные операторы, `break` завершает выполнение только того оператора `do`, `for`, `switch` или `while`, который непосредственно его окружает.  Передать управление из более глубоко вложенных структур можно при помощи оператора `return` или `goto`.  
  
## Пример  
 В следующем коде показан способ использования оператора `break` в цикле `for`.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main()  
{  
    // An example of a standard for loop  
    for (int i = 1; i < 10; i++)  
    {  
        cout << i << '\n';  
        if (i == 4)  
            break;  
    }  
  
    // An example of a range-based for loop  
int nums []{1, 2, 3, 4, 5, 6, 7, 8, 9, 10};  
  
    for (int i : nums) {  
        if (i == 4) {  
            break;  
        }  
        cout << i << '\n';  
    }  
}  
```  
  
  **В каждом случае:**   
**1**  
**2**  
**3** В следующем коде показан способ использования оператора `break` в цикле `while` и цикле `do`.  
  
```cpp  
  
#include <iostream>  
using namespace std;  
  
int main() {  
    int i = 0;  
  
    while (i < 10) {  
        if (i == 4) {  
            break;  
        }  
        cout << i << '\n';  
        i++;  
    }  
  
    i = 0;  
    do {  
        if (i == 4) {  
            break;  
        }  
        cout << i << '\n';  
        i++;  
    } while (i < 10);  
}  
```  
  
  **В каждом случае:**  
**0**  
**1**  
**2**  
**3** В следующем коде показан способ использования оператора `break` в операторе switch.  Необходимо использовать `break` всегда, когда необходимо обработать каждый случай по отдельности; если `break` не используется, выполнение кода продолжится до следующего случая.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
enum Suit{ Diamonds, Hearts, Clubs, Spades };  
  
int main() {  
  
    Suit hand;  
    . . .  
    // Assume that some enum value is set for hand  
    // In this example, each case is handled separately  
    switch (hand)  
    {  
    case Diamonds:  
        cout << "got Diamonds \n";  
        break;  
    case Hearts:  
        cout << "got Hearts \n";  
        break;  
    case Clubs:  
        cout << "got Clubs \n";  
        break;  
    case Spades:  
        cout << "got Spades \n";  
        break;  
    default:   
          cout << "didn't get card \n";  
    }  
    // In this example, Diamonds and Hearts are handled one way, and  
    // Clubs, Spades, and the default value are handled another way  
    switch (hand)  
    {  
    case Diamonds:  
    case Hearts:  
        cout << "got a red card \n";  
        break;  
    case Clubs:  
    case Spades:   
    default:  
        cout << "didn't get a red card \n";  
    }  
}  
```  
  
## См. также  
 [Операторы перехода](../cpp/jump-statements-cpp.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)   
 [Оператор continue](../cpp/continue-statement-cpp.md)