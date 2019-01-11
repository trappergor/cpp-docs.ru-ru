---
title: Переносимость на границах API (современный C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: abbd405e-3038-427c-8c24-e00598f0936a
ms.openlocfilehash: 3f72bc32e436c2f7a2f76ed6bbb9553b5e5be6b8
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220313"
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

[Возвращение к C++ (современный C++)](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[Справочник по языку C++](../cpp/cpp-language-reference.md)<br/>
[Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)
