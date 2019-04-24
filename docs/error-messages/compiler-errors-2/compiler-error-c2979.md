---
title: Ошибка компилятора C2979
ms.date: 11/04/2016
f1_keywords:
- C2979
helpviewer_keywords:
- C2979
ms.assetid: 98bd9043-ec44-451e-a482-3a8e35fc7464
ms.openlocfilehash: e9b0af0d17ef57f19e051165b16632e3180159cd
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776625"
---
# <a name="compiler-error-c2979"></a>Ошибка компилятора C2979

явные специализации не поддерживаются в универсальных шаблонах

Универсальный класс был объявлен неправильно.  См. в разделе [универсальные шаблоны](../../extensions/generics-cpp-component-extensions.md) Дополнительные сведения.

## <a name="example"></a>Пример

При компиляции следующего примера возникнет ошибка C2979.

```
// C2979.cpp
// compile with: /clr /c
generic <>
ref class Utils {};   // C2979 error

generic <class T>
ref class Utils2 {};   // OK
```