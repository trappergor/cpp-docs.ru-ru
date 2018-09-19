---
title: Ошибка компилятора C2932 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2932
dev_langs:
- C++
helpviewer_keywords:
- C2932
ms.assetid: c28e88d9-e654-4367-bfb4-13c780bca9bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 48c7655703774661ef6a5586f83a05e79585ce9f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043005"
---
# <a name="compiler-error-c2932"></a>Ошибка компилятора C2932

"класс": идентификатор класса типа переопределен как элемент данных "идентификатор"

Универсальный класс или класс шаблона нельзя использовать в качестве элемента данных.

Следующий пример приводит к возникновению ошибки C2932:

```
// C2932.cpp
// compile with: /c
template<class T>
struct TC {};

struct MyStruct {
   int TC<int>;   // C2932
   int TC;   // OK
};
```

Ошибка C2932 также может возникнуть при использовании универсальных шаблонов:

```
// C2932b.cpp
// compile with: /clr /c
generic<class T>
ref struct GC {};

struct MyStruct {
   int GC<int>;   // C2932
   int GC;   // OK
};
```