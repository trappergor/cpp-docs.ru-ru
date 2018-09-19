---
title: Ошибка компилятора C2535 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2535
dev_langs:
- C++
helpviewer_keywords:
- C2535
ms.assetid: a958f83e-e2bf-4a59-b44b-d406ec325d7e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98e1920b2163a318fbdba3b64d56bf74a8cd809f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085905"
---
# <a name="compiler-error-c2535"></a>Ошибка компилятора C2535

«Идентификатор»: функция-член уже определена или объявлена

Эта ошибка может быть вызвано, используя один и тот же список формальных параметров в более одного определения или объявления перегруженной функции.

Если C2535 возникает из-за функции Dispose, см. в разделе [деструкторы и методы завершения](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) Дополнительные сведения.

При компиляции проекта ATL, см. в статье базы знаний Q241852.

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