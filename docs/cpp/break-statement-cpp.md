---
title: "Оператор break (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- break_cpp
dev_langs:
- C++
helpviewer_keywords:
- break keyword [C++]
ms.assetid: 63739928-8985-4b05-93ce-016322e6da3d
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 2e016ccc90ef53ca5f269a73d3f5b7ed3185f550
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="break-statement-c"></a>Оператор break (C++)
Оператор `break` завершает выполнение ближайшего внешнего цикла или условного оператора, в котором он находится. Управление передается оператору, который расположен после оператора, при его наличии.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
break;  
```  
  
## <a name="remarks"></a>Примечания  
 `break` Оператор используется с условным [переключения](../cpp/switch-statement-cpp.md) инструкции и с [сделать](../cpp/do-while-statement-cpp.md), [для](../cpp/for-statement-cpp.md), и [при](../cpp/while-statement-cpp.md) цикла инструкции.  
  
 В операторе `switch` оператор `break` заставляет программу выполнять следующий оператор, находящийся снаружи оператора `switch`. Без оператора `break` выполняется каждый оператор из сопоставленной метки `case` до конца оператора `switch`, включая предложение `default`.  
  
 В циклах оператор `break` завершает выполнение ближайшего внешнего оператора `do`, `for` или `while`. Управление передается оператору, который расположен после завершенного оператора, при его наличии.  
  
 Если используются вложенные операторы, `break` завершает выполнение только того оператора `do`, `for`, `switch` или `while`, который непосредственно его окружает. Передать управление из более глубоко вложенных структур можно при помощи оператора `return` или `goto`.  
  
## <a name="example"></a>Пример  
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
  
```Output  
In each case:   
1  
2  
3  
```  
  
 В следующем коде показан способ использования оператора `break` в цикле `while` и цикле `do`.  
  
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
  
```Output  
In each case:  
0123  
```  
  
 В следующем коде показан способ использования оператора `break` в операторе switch. Необходимо использовать `break` всегда, когда необходимо обработать каждый случай по отдельности; если `break` не используется, выполнение кода продолжится до следующего случая.  
  
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
  
## <a name="see-also"></a>См. также  
 [Операторы перехода](../cpp/jump-statements-cpp.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Оператор continue](../cpp/continue-statement-cpp.md)
