---
title: Переносимость на границах API (современный C++) | Документы Microsoft
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
ms.openlocfilehash: c214ed18e5afec51f52514abdd73e0e5b658635a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="portability-at-abi-boundaries-modern-c"></a>Переносимость на границах API (современный C++)
Используйте границы двоичного интерфейса достаточно переносимые типы и соглашения. «Переносимый тип» является встроенным типом C или структура, которая содержит только встроенные типы C. Типы классов можно использовать только в том случае, когда вызывающий и вызываемый объекты согласны на макет, вызвав соглашение и т. д. Это возможно только, когда оба компилируются с помощью компилятора и параметры компилятора.  
  
## <a name="how-to-flatten-a-class-for-c-portability"></a>Спрямление класса для обеспечения переносимости C  
 Когда вызывающим объектам может компилироваться с помощью другого компилятора и язык, а затем «сведение» для **extern «C»** API с определенным соглашением о вызовах:  
  
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
 [Возвращение к C++](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [Справочник по языку C++](../cpp/cpp-language-reference.md)   
 [Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)