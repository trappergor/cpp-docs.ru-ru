---
title: Переносимость на границах ABI
description: Сведение C++ интерфейсов к соглашениям о вызовах C в границах двоичного интерфейса.
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: abbd405e-3038-427c-8c24-e00598f0936a
ms.openlocfilehash: b3b2b217739ff5900c8ef0329ff3e8909a3fe036
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303320"
---
# <a name="portability-at-abi-boundaries"></a>Переносимость на границах ABI

Используйте достаточно переносимые типы и соглашения на границах двоичного интерфейса. "Portable Type" — это встроенный тип C или структура, содержащая только встроенные типы C. Типы классов можно использовать, только когда вызывающий и вызываемый принимает на себя макет, соглашение о вызовах и т. д. Это возможно только в том случае, если оба скомпилированы с одинаковыми параметрами компилятора и компилятора.

## <a name="how-to-flatten-a-class-for-c-portability"></a>Как свести класс к переносимости на C

Если вызывающие объекты могут быть скомпилированы с другим компилятором или языком, то "сведение" к внешнему API **"C"** с определенным соглашением о вызовах:

```cpp
// class widget {
//   widget();
//   ~widget();
//   double method( int, gadget& );
// };
extern "C" {        // functions using explicit "this"
   struct widget;   // opaque type (forward declaration only)
   widget* STDCALL widget_create();      // constructor creates new "this"
   void STDCALL widget_destroy(widget*); // destructor consumes "this"
   double STDCALL widget_method(widget*, int, gadget*); // method uses "this"
}
```

## <a name="see-also"></a>См. также:

[Добро пожаловать обратно вC++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[Справочник по языку C++](../cpp/cpp-language-reference.md)<br/>
[Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)
