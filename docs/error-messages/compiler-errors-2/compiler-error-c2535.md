---
title: Ошибка компилятора C2535
ms.date: 11/04/2016
f1_keywords:
- C2535
helpviewer_keywords:
- C2535
ms.assetid: a958f83e-e2bf-4a59-b44b-d406ec325d7e
ms.openlocfilehash: b2b5452cfe59284d56b019674ffbabbda0dc62d1
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344707"
---
# <a name="compiler-error-c2535"></a>Ошибка компилятора C2535

«Идентификатор»: функция-член уже определена или объявлена

Эта ошибка может быть вызвано, используя один и тот же список формальных параметров в более одного определения или объявления перегруженной функции.

Если C2535 возникает из-за функции Dispose, см. в разделе [деструкторы и методы завершения](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) Дополнительные сведения.

Следующий пример приводит к возникновению ошибки C2535:

```
// C2535.cpp
// compile with: /c
class C {
public:
   void func();   // forward declaration
   void func() {}   // C2535
};
```