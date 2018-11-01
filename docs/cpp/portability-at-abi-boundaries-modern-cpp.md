---
title: Переносимость на границах API (современный C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: abbd405e-3038-427c-8c24-e00598f0936a
ms.openlocfilehash: 12f60b92e71c15a94546e5b099c3b49e3685b68b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549959"
---
# <a name="portability-at-abi-boundaries-modern-c"></a>Переносимость на границах API (современный C++)

Используйте на границах двоичный интерфейс достаточно переносимые типы и соглашения. «Переносимый тип» является встроенным типом C или структуру, содержащую только встроенные типы C. Типы классов можно использовать только в том случае, когда вызывающий и вызываемый объекты согласовать макета, вызвав соглашение и т. д. Это возможно, только если оба компилируются с тем же компилятора и параметры компилятора.

## <a name="how-to-flatten-a-class-for-c-portability"></a>Спрямление класса для обеспечения переносимости C

Если вызывающим объектам может быть скомпилирован с помощью другого компилятора/языка, а затем «уплощения», чтобы **extern «C»** API с определенным соглашением о вызовах:

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

## <a name="see-also"></a>См. также

[Возвращение к C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[Справочник по языку C++](../cpp/cpp-language-reference.md)<br/>
[Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)