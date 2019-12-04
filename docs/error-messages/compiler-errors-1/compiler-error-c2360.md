---
title: Ошибка компилятора C2360
ms.date: 11/04/2016
f1_keywords:
- C2360
helpviewer_keywords:
- C2360
ms.assetid: 51bfd2ee-8108-4777-aa93-148b9cebfa83
ms.openlocfilehash: 226fcd8a27c9abdb789b8191a5cf4e59cc4a66cc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759910"
---
# <a name="compiler-error-c2360"></a>Ошибка компилятора C2360

Инициализация "идентификатор" пропускается меткой "Case"

Инициализацию `identifier` можно пропустить в инструкции `switch`. Нельзя перейти к предшествующему объявлению с инициализатором, если объявление не заключено в блок. (Если только он не объявлен в блоке, переменная находится в пределах области до конца оператора `switch`.)

Следующий пример приводит к возникновению ошибки C2360:

```cpp
// C2360.cpp
int main() {
   int x = 0;
   switch ( x ) {
   case 0 :
      int i = 1;
      { int j = 1; }
   case 1 :   // C2360
      int k = 1;
   }
}
```

Возможное решение

```cpp
// C2360b.cpp
int main() {
   int x = 0;
   switch ( x ) {
   case 0 :
      { int j = 1; int i = 1;}
   case 1 :
      int k = 1;
   }
}
```
