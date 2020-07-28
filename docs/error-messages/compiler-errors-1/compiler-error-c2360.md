---
title: Ошибка компилятора C2360
ms.date: 11/04/2016
f1_keywords:
- C2360
helpviewer_keywords:
- C2360
ms.assetid: 51bfd2ee-8108-4777-aa93-148b9cebfa83
ms.openlocfilehash: a2a164f919dc7535a4587d51f4f7dba8653a1760
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214689"
---
# <a name="compiler-error-c2360"></a>Ошибка компилятора C2360

Инициализация "идентификатор" пропускается меткой "Case"

Инициализацию `identifier` можно пропустить в **`switch`** операторе. Нельзя перейти к предшествующему объявлению с инициализатором, если объявление не заключено в блок. (Если только он не объявлен в блоке, переменная находится в пределах области до конца **`switch`** оператора.)

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

Возможное решение:

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
