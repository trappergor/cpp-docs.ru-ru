---
title: Переносимость на границах API (современный C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: abbd405e-3038-427c-8c24-e00598f0936a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 891f56d763fc86efd62fb5bae3b21498336a8ccc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058423"
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