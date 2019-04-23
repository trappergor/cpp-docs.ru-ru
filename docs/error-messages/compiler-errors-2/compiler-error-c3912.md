---
title: Ошибка компилятора C3912
ms.date: 11/04/2016
f1_keywords:
- C3912
helpviewer_keywords:
- C3912
ms.assetid: 674e050c-11fb-4db1-8bdf-a3e95b41161d
ms.openlocfilehash: bd66196c35715304577b8f6785261be8bdcdafec
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59775860"
---
# <a name="compiler-error-c3912"></a>Ошибка компилятора C3912

«событие»: тип события должен быть типом делегата

Событие было объявлено, но не соответствующего типа.

Дополнительные сведения см. в разделе [событий](../../extensions/event-cpp-component-extensions.md).

Следующий пример приводит к возникновению ошибки C3912:

```
// C3912.cpp
// compile with: /clr
delegate void H();
ref class X {
   event int Ev;   // C3912
   event H^ Ev2;   // OK
};
```