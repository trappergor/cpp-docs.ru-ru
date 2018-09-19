---
title: Ошибка компилятора C2939 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2939
dev_langs:
- C++
helpviewer_keywords:
- C2939
ms.assetid: 455b050b-f2dc-4b5b-bd6a-e1f81d3d1644
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b7d397eff2cfe561ace6f29b00601941779ef2b2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053158"
---
# <a name="compiler-error-c2939"></a>Ошибка компилятора C2939

"класс": идентификатор класса типа переопределен как локальная переменная данных

Универсальный класс или класс шаблона нельзя использовать в качестве локальной переменной данных.

Эта ошибка может возникнуть при неправильной расстановке скобок.

В следующем примере возникает ошибка C2939:

```
// C2939.cpp
template<class T>
struct TC { };
int main() {
   int TC<int>;   // C2939
   int TC;   // OK
}
```

Ошибка C2939 также может возникнуть при использовании универсальных шаблонов:

```
// C2939b.cpp
// compile with: /clr
generic<class T>
ref struct GC { };

int main() {
   int GC<int>;   // C2939
   int GC;   // OK
}
```