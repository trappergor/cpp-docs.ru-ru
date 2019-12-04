---
title: Ошибка компилятора C3625
ms.date: 11/04/2016
f1_keywords:
- C3625
helpviewer_keywords:
- C3625
ms.assetid: fdf49f21-d6b1-42f4-9eec-23b04ae8b4aa
ms.openlocfilehash: 83b6756c75f90380024a8f31df62290bed1f7738
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761911"
---
# <a name="compiler-error-c3625"></a>Ошибка компилятора C3625

native_type: неуправляемый тип не может быть производным от типа WinRT type

Неуправляемый класс не может наследовать от управляемого класса или класса WinRT. Дополнительные сведения см. в статье [Классы и структуры](../../extensions/classes-and-structs-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3625:

```cpp
// C3625.cpp
// compile with: /clr /c
ref class B {};
class D : public B {};   // C3625 cannot inherit from a managed class
```
