---
title: Оператор break (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- break_cpp
dev_langs:
- C++
helpviewer_keywords:
- break keyword [C++]
ms.assetid: 63739928-8985-4b05-93ce-016322e6da3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 30910f6850fc3728ee101ab0662638fdebcd3775
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405448"
---
# <a name="break-statement-c"></a>Оператор break (C++)
**Break** инструкция завершает выполнение ближайшего внешнего цикла или условного оператора, в котором он находится. Управление передается оператору, который расположен после оператора, при его наличии.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
break;  
```  
  
## <a name="remarks"></a>Примечания  
 **Break** оператор используется с условным [переключения](../cpp/switch-statement-cpp.md) инструкции и с [сделать](../cpp/do-while-statement-cpp.md), [для](../cpp/for-statement-cpp.md), и [при](../cpp/while-statement-cpp.md) операторы цикла.  
  
 В **переключения** инструкции **break** заставляет программу для выполнения следующего оператора за пределами **переключения** инструкции. Без **break** инструкции, каждый оператор из сопоставленной **случай** метки в конец **переключения** инструкции, включая **по умолчанию**предложение, выполняется.  
  
 В циклах **break** инструкция завершает выполнение ближайшего внешнего оператора **сделать**, **для**, или **хотя** инструкции. Управление передается оператору, который расположен после завершенного оператора, при его наличии.  
  
 Используются вложенные операторы **break** инструкция завершает выполнение только **сделать**, **для**, **переключения**, или **при**оператор, который непосредственно его окружает. Можно использовать **возвращают** или **goto** инструкцию, чтобы передать управление из более глубоко вложенных структур.  
  
## <a name="example"></a>Пример  
 Ниже показано, как использовать **break** инструкции в **для** цикла.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main()  
{  
    // An example of a standard for loop  
    for (int i = 1; i < 10; i++)  
    {  
        if (i == 4) {  
            break;  
        }  
        cout << i << '\n';  
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
  
 Ниже показано, как использовать **break** в **хотя** цикла и **сделать** цикла.  
  
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
  
 Ниже показано, как использовать **break** в операторе switch. Необходимо использовать **break** во всех случаях, если вы хотите обрабатывать каждый случай раздельно; Если вы не используете **break**, выполнение кода продолжится до следующего случая.  
  
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