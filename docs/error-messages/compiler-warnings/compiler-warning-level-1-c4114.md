---
title: Предупреждение компилятора (уровень 1) C4114
ms.date: 11/04/2016
f1_keywords:
- C4114
helpviewer_keywords:
- C4114
ms.assetid: 3983e1c6-e8bb-46dc-8894-e1827db48797
ms.openlocfilehash: 8d2b0339ff3cce9a68dce57a5f2b4efac076c5c2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233318"
---
# <a name="compiler-warning-level-1-c4114"></a>Предупреждение компилятора (уровень 1) C4114

Множественное использование одного и того же квалификатора типа

В объявлении типа или определении используется квалификатор типа ( **`const`** , **`volatile`** , **`signed`** или **`unsigned`** ) более одного раза. Это вызывает предупреждение с расширениями Майкрософт (/Ze) и ошибкой в режиме совместимости с ANSI (/ZA).

Следующий пример приводит к возникновению ошибки C4114:

```cpp
// C4114.cpp
// compile with: /W1 /c
volatile volatile int i;   // C4114
```

Следующий пример приводит к возникновению ошибки C4114:

```cpp
// C4114_b.cpp
// compile with: /W1 /c
static const int const * ii;   // C4114
static const int * const iii;   // OK
```
