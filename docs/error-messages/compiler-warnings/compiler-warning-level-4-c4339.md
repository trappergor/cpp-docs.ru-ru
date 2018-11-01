---
title: Предупреждение компилятора (уровень 4) C4339
ms.date: 11/04/2016
f1_keywords:
- C4339
helpviewer_keywords:
- C4339
ms.assetid: 5b83353d-7777-4afb-8476-3c368349028c
ms.openlocfilehash: bc9d335b3a09f7953a12b388d5bb40cc4d433969
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50567769"
---
# <a name="compiler-warning-level-4-c4339"></a>Предупреждение компилятора (уровень 4) C4339

type: обнаружено использование неопределенного типа в метаданных WinRT или CLR; применение этого типа может вызвать исключение при выполнении

Тип не был определен в коде, который был скомпилирован для среды выполнения Windows или среды CLR. Определите тип, чтобы избежать возможных исключений среды выполнения.

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

В следующем примере показано возникновение ошибки C4339 и приводятся сведения по ее устранению.

```
// C4339.cpp
// compile with: /W4 /clr /c
// C4339 expected
#pragma warning(default : 4339)

// Delete the following line to resolve.
class A;

// Uncomment the following line to resolve.
// class A{};

class X {
public:
   X() {}

   virtual A *mf() {
      return 0;
   }
};

X * f() {
   return new X();
}
```