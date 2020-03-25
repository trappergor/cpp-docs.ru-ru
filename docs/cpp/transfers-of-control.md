---
title: Передача управления
ms.date: 11/04/2016
helpviewer_keywords:
- control flow, branching
- control flow, transferring control
ms.assetid: aa51e7f2-060f-4106-b0fe-331f04357423
ms.openlocfilehash: c9a46ccb1cf519080c5105855e41ecd3ebc23f77
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188055"
---
# <a name="transfers-of-control"></a>Передача управления

Можно использовать инструкцию **goto** или метку **case** в операторе **switch** для указания программы, которая выполняет ветвление после инициализатора. Такой код не допускается, если объявление, содержащее инициализатор, не будет находиться в блоке, заключенном в блоке, в котором выполняется оператор jump.

В следующем примере показан цикл, в котором выполняется объявление и инициализация объектов `total`, `ch` и `i`. Существует также ошибочный оператор **goto** , который передает управление после инициализатора.

```cpp
// transfers_of_control.cpp
// compile with: /W1
// Read input until a nonnumeric character is entered.
int main()
{
   char MyArray[5] = {'2','2','a','c'};
   int i = 0;
   while( 1 )
   {
      int total = 0;

      char ch = MyArray[i++];

      if ( ch >= '0' && ch <= '9' )
      {
         goto Label1;

         int i = ch - '0';
      Label1:
         total += i;   // C4700: transfers past initialization of i.
      } // i would be destroyed here if  goto error were not present
   else
      // Break statement transfers control out of loop,
      //  destroying total and ch.
      break;
   }
}
```

В предыдущем примере инструкция **goto** пытается передавать управление после инициализации `i`. Однако если бы объект `i` был объявлен, но не инициализирован, передача была бы допустима.

Объекты `total` и `ch`, объявленные в блоке, который служит в качестве *инструкции* инструкции **while** , уничтожаются при выходе из этого блока с помощью инструкции **break** .
