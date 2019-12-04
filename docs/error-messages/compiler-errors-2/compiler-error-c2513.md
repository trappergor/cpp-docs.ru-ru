---
title: Ошибка компилятора C2513
ms.date: 11/04/2016
f1_keywords:
- C2513
helpviewer_keywords:
- C2513
ms.assetid: ab5b21d3-61e2-4df7-8eea-6f14d6ba8620
ms.openlocfilehash: 093a5856fdcfa6311fcef93214672b035c91b4fc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746530"
---
# <a name="compiler-error-c2513"></a>Ошибка компилятора C2513

"тип": не объявлена переменная перед "="

Описатель типа отображается в объявлении без идентификатора переменной.

Следующий пример приводит к возникновению ошибки C2513:

```cpp
// C2513.cpp
int main() {
   int = 9;   // C2513
   int i = 9;   // OK
}
```

Эта ошибка также может быть вызвана работой по согласованности компилятора, выполненной для Visual Studio .NET 2003: инициализация typedef больше не разрешена. Инициализация typedef не разрешена стандартом и теперь приводит к ошибке компилятора.

```cpp
// C2513b.cpp
// compile with: /c
typedef struct S {
   int m_i;
} S = { 1 };   // C2513
// try the following line instead
// } S;
```

В качестве альтернативы можно удалить `typedef`, чтобы определить переменную со списком агрегатных инициализаторов, но это не рекомендуется, так как он создает переменную с тем же именем, что и тип, и скрывает имя типа.
