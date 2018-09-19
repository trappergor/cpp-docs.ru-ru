---
title: Ошибка компилятора C3670 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3670
dev_langs:
- C++
helpviewer_keywords:
- C3670
ms.assetid: d0fa9c6e-8f90-48c7-9066-31b4fa5942eb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1129a25e628710121d667a44022eec5a0450b092
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115337"
---
# <a name="compiler-error-c3670"></a>Ошибка компилятора C3670

«override»: невозможно переопределить недоступный метод базового класса «метод»

Переопределение может происходить только в функции с уровнем доступа доступны в производном типе. Дополнительные сведения см. в разделе [явное переопределение](../../windows/explicit-overrides-cpp-component-extensions.md).

Следующий пример приводит к возникновению ошибки C3670:

```
// C3670.cpp
// compile with: /clr /c
public ref class C {
// Uncomment the following line to resolve.
// public:
   virtual void g() { }
};

public ref class D : public C {
public:
   virtual void f() new sealed = C::g {};   // C3670
};
```