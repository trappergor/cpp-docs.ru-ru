---
title: Передача управления
ms.date: 11/04/2016
helpviewer_keywords:
- control flow, branching
- control flow, transferring control
ms.assetid: aa51e7f2-060f-4106-b0fe-331f04357423
ms.openlocfilehash: ef437d0a691ceff72485be1ff9584052f540031a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232187"
---
# <a name="transfers-of-control"></a>Передача управления

Можно использовать **`goto`** оператор или **`case`** метку в **`switch`** операторе, чтобы указать программу, которая выполняет ветвление после инициализатора. Такой код не допускается, если объявление, содержащее инициализатор, не будет находиться в блоке, заключенном в блоке, в котором выполняется оператор jump.

В следующем примере показан цикл, в котором выполняется объявление и инициализация объектов `total`, `ch` и `i`. Существует также ошибочный **`goto`** оператор, который передает управление после инициализатора.

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

В предыдущем примере **`goto`** Инструкция пытается переслать управление после инициализации `i` . Однако если бы объект `i` был объявлен, но не инициализирован, передача была бы допустима.

Объекты `total` и `ch` , объявленные в блоке, который выступает в качестве *инструкции* **`while`** инструкции, уничтожаются при выходе из этого блока с помощью **`break`** инструкции.
