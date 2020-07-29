---
title: Ошибка компилятора C2513
ms.date: 11/04/2016
f1_keywords:
- C2513
helpviewer_keywords:
- C2513
ms.assetid: ab5b21d3-61e2-4df7-8eea-6f14d6ba8620
ms.openlocfilehash: 96f2ccc29eed5c1fa4e29f69d18ae6503417f211
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212726"
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

В качестве альтернативы можно удалить, **`typedef`** чтобы определить переменную со списком агрегатных инициализаторов, но это не рекомендуется, так как он создает переменную с тем же именем, что и тип, и скрывает имя типа.
