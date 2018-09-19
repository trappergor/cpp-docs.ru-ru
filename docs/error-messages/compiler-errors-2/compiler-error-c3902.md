---
title: Ошибка компилятора C3902 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3902
dev_langs:
- C++
helpviewer_keywords:
- C3902
ms.assetid: feb3bb29-f836-4d77-ba71-3876f7f4f216
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5998c0836f3adfbf047cc7259b032258a584f272
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070045"
---
# <a name="compiler-error-c3902"></a>Ошибка компилятора C3902

«метод_доступа»: тип последнего параметра должен быть «тип»

Тип последнего параметра по крайней мере один метод set должен соответствовать типу свойства. Дополнительные сведения см. в разделе [property](../../windows/property-cpp-component-extensions.md).

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