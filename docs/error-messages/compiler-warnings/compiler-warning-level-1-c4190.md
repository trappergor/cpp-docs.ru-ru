---
title: Предупреждение компилятора (уровень 1) C4190
ms.date: 11/04/2016
f1_keywords:
- C4190
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
ms.openlocfilehash: 8187926f2477a4d3f1ca3019cc8c3c71710c1dff
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233305"
---
# <a name="compiler-warning-level-1-c4190"></a>Предупреждение компилятора (уровень 1) C4190

"идентификатор1" имеет указанную компоновку C, но возвращает определяемый пользователем тип "идентификатор2", который несовместим с C

Функция или указатель на функцию имеют ОПРЕДЕЛЯЕМый пользователем тип, который является классом, структурой, перечислением или объединением, в качестве типа возвращаемого значения и `extern "C"` компоновки. Это допустимо, если:

- Все вызовы этой функции осуществляются из C++.

- Определение функции находится в C++.

## <a name="example"></a>Пример

```cpp
// C4190.cpp
// compile with: /W1 /LD
struct X
{
   int i;
   X ();
   virtual ~X ();
};

extern "C" X func ();   // C4190
```
