---
title: Ошибка компилятора C3142
ms.date: 11/04/2016
f1_keywords:
- C3142
helpviewer_keywords:
- C3142
ms.assetid: 795137ad-d00a-4a9c-9665-0cd8bfb5da8b
ms.openlocfilehash: 38bf40b6e1b7495232d7c33317408b872081e9f1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374954"
---
# <a name="compiler-error-c3142"></a>Ошибка компилятора C3142

«Имя»: невозможно получить адрес свойства

Адрес свойства недоступен для разработчика.

Следующий пример приводит к возникновению ошибки C3142:

```
// C3142_2.cpp
// compile with: /clr
using namespace System;
ref class CSize {
private:
   property int Size {
      int get();
   }
};

int main() {
    &CSize::Size; // C3142
}
```
