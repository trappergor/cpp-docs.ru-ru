---
title: Ошибка компилятора C2361
ms.date: 11/04/2016
f1_keywords:
- C2361
helpviewer_keywords:
- C2361
ms.assetid: efbdaeb9-891c-4f7d-97da-89088a8413f3
ms.openlocfilehash: ca03a42cbf746a1ef32d9c79c23de637f05b56fc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597110"
---
# <a name="compiler-error-c2361"></a>Ошибка компилятора C2361

Пропуск инициализации «идентификатор» метки «default»

Инициализация `identifier` может быть пропущено в `switch` инструкции. Нельзя перейти назад объявление с помощью инициализатора, только если объявление в блоке. (Если она не объявлена в блоке, переменная находится в пределах области до конца `switch` инструкции.)

Следующий пример приводит к возникновению ошибки C2361:

```
// C2361.cpp
void func( void ) {
   int x;
   switch (x) {
   case 0 :
      int i = 1;
      { int j = 1; }
   default :   // C2361 error
      int k = 1;
   }
}
```

Возможное решение

```
// C2361b.cpp
// compile with: /c
void func( void ) {
   int x = 0;
   switch (x) {
   case 0 :
      { int j = 1; int i = 1;}
   default :
      int k = 1;
   }
}
```