---
title: Ошибка компилятора C2360
ms.date: 11/04/2016
f1_keywords:
- C2360
helpviewer_keywords:
- C2360
ms.assetid: 51bfd2ee-8108-4777-aa93-148b9cebfa83
ms.openlocfilehash: 6e956ccb021dc3bce4d107e4aa6e0bbe4356283b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364731"
---
# <a name="compiler-error-c2360"></a>Ошибка компилятора C2360

Пропуск инициализации «идентификатор» метки «case»

Инициализация `identifier` может быть пропущено в `switch` инструкции. Нельзя перейти назад объявление с помощью инициализатора, только если объявление в блоке. (Если она не объявлена в блоке, переменная находится в пределах области до конца `switch` инструкции.)

Следующий пример приводит к возникновению ошибки C2360:

```
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

```
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