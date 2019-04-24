---
title: Ошибка компилятора C3902
ms.date: 11/04/2016
f1_keywords:
- C3902
helpviewer_keywords:
- C3902
ms.assetid: feb3bb29-f836-4d77-ba71-3876f7f4f216
ms.openlocfilehash: d90bf299c566ce72e3d1cbfeb545def0a43d6cbf
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776994"
---
# <a name="compiler-error-c3902"></a>Ошибка компилятора C3902

«метод_доступа»: тип последнего параметра должен быть «тип»

Тип последнего параметра по крайней мере один метод set должен соответствовать типу свойства. Дополнительные сведения см. в разделе [property](../../extensions/property-cpp-component-extensions.md).

Следующий пример приводит к возникновению ошибки C3902:

```
// C3902.cpp
// compile with: /clr /c
using namespace System;
ref class X {
   property String ^Name {
      void set(int);   // C3902
      // try the following line instead
      // void set(String^){}
   }

   property double values[int,int] {
      void set(int, int, float);   // C3902
      // try the following line instead
      // void set(int, int, double){}
   }
};
```