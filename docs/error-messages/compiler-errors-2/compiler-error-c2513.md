---
title: Ошибка компилятора C2513
ms.date: 11/04/2016
f1_keywords:
- C2513
helpviewer_keywords:
- C2513
ms.assetid: ab5b21d3-61e2-4df7-8eea-6f14d6ba8620
ms.openlocfilehash: 13840246a5dc6a1c1bdbcb55dc47f212ee353d81
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165220"
---
# <a name="compiler-error-c2513"></a>Ошибка компилятора C2513

«Тип»: нет переменных, объявленных перед «=»

Спецификатор типа в объявлении не имеет идентификатора переменной.

Следующий пример приводит к возникновению ошибки C2513:

```
// C2513.cpp
int main() {
   int = 9;   // C2513
   int i = 9;   // OK
}
```

Эта ошибка также может возникать в результате изменений работы компилятора, в Visual Studio .NET 2003: инициализация typedef не допускается. Инициализация typedef не допускается согласно стандарту и теперь приводит к ошибке компилятора.

```
// C2513b.cpp
// compile with: /c
typedef struct S {
   int m_i;
} S = { 1 };   // C2513
// try the following line instead
// } S;
```

Или же можно удалить `typedef` определить переменную с помощью списка инициализаторов статистических выражений, но это не рекомендуется, поскольку создает переменную с тем же именем, что тип и скрыть имя типа.