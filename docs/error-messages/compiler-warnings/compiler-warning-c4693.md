---
title: Предупреждение компилятора C4693
ms.date: 10/25/2017
f1_keywords:
- C4693
helpviewer_keywords:
- C4693
ms.assetid: 72d8db01-5e6f-4794-8731-76107e8f064a
ms.openlocfilehash: 71c3db18b400ce94bff3c643d6728a6613061039
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165136"
---
# <a name="compiler-warning-c4693"></a>Предупреждение компилятора C4693

> "класс": у запечатанного абстрактного класса не может быть членов экземпляра "Тест"

Если тип помечен как [sealed](../../extensions/sealed-cpp-component-extensions.md) и [abstract](../../extensions/abstract-cpp-component-extensions.md), он может иметь только статические члены.

Это предупреждение автоматически повышается до ошибки. Если вы хотите изменить это поведение, используйте [#pragma предупреждение](../../preprocessor/warning.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению предупреждения C4693:

```cpp
// C4693.cpp
// compile with: /clr /c
public ref class Public_Ref_Class sealed abstract {
public:
   void Test() {}   // C4693
   static void Test2() {}   // OK
};
```
