---
title: Ошибка компилятора C2991
ms.date: 11/04/2016
f1_keywords:
- C2991
helpviewer_keywords:
- C2991
ms.assetid: a87e4404-26e8-4927-b3ee-5d02b3b8bee1
ms.openlocfilehash: 8a6cf04d89cd18cb5374f2d930b5395a297ce8f5
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751512"
---
# <a name="compiler-error-c2991"></a>Ошибка компилятора C2991

переопределение параметра типа "параметр"

Произошел конфликт типов между двумя определениями универсальных параметров или параметров шаблона `parameter`. При определении нескольких универсальных параметров или параметров шаблона необходимо использовать эквивалентные типы.

Следующий пример приводит к возникновению ошибки C2991:

```cpp
// C2991.cpp
// compile with: /c
template<class T, class T> struct TC {};   // C2991
// try the following line instead
// template<class T, class T2> struct TC {};
```

Ошибка C2991 также может возникнуть при использовании универсальных шаблонов.

```cpp
// C2991b.cpp
// compile with: /clr /c
generic<class T,class T> ref struct GC {};   // C2991
// try the following line instead
// generic<class T,class T2> ref struct GC {};
```
