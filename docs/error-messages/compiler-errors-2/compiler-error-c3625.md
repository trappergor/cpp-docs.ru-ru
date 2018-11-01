---
title: Ошибка компилятора C3625
ms.date: 11/04/2016
f1_keywords:
- C3625
helpviewer_keywords:
- C3625
ms.assetid: fdf49f21-d6b1-42f4-9eec-23b04ae8b4aa
ms.openlocfilehash: 08ad1d09cb9149811566f67a585a718340254de9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50635408"
---
# <a name="compiler-error-c3625"></a>Ошибка компилятора C3625

native_type: неуправляемый тип не может быть производным от типа WinRT type

Неуправляемый класс не может наследовать от управляемого класса или класса WinRT. Дополнительные сведения см. в разделе [классы и структуры](../../windows/classes-and-structs-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3625:

```
// C3625.cpp
// compile with: /clr /c
ref class B {};
class D : public B {};   // C3625 cannot inherit from a managed class
```
