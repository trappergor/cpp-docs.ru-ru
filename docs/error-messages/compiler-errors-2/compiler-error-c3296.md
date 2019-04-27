---
title: Ошибка компилятора C3296
ms.date: 11/04/2016
f1_keywords:
- C3296
helpviewer_keywords:
- C3296
ms.assetid: fc4c9dcd-16cf-4eee-a1ac-c43e7c29e443
ms.openlocfilehash: c0a162590ac2a72dda17b2ecfc96899e94cde24c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222548"
---
# <a name="compiler-error-c3296"></a>Ошибка компилятора C3296

"свойство": свойство с таким именем уже существует

Компилятор обнаружил несколько свойств с одинаковым именем. Каждое свойство в типе должно иметь уникальное имя.

Дополнительные сведения см. в разделе [property](../../extensions/property-cpp-component-extensions.md).

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3296:

```
// C3296.cpp
// compile with: /clr /c
using namespace System;

ref class R {
public:
   property int MyProp[int] { int get(int); }

   property String^ MyProp[int] { void set(int, String^); }   // C3296
};
```