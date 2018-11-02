---
title: Предупреждение компилятора C4693
ms.date: 10/25/2017
f1_keywords:
- C4693
helpviewer_keywords:
- C4693
ms.assetid: 72d8db01-5e6f-4794-8731-76107e8f064a
ms.openlocfilehash: 49d101ea56cd868e18489b6c74724a2d106c9265
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536663"
---
# <a name="compiler-warning-c4693"></a>Предупреждение компилятора C4693

> "класс": у запечатанного абстрактного класса не может быть членов экземпляра "Тест"

Если тип помечен [запечатанный](../../windows/sealed-cpp-component-extensions.md) и [абстрактный](../../windows/abstract-cpp-component-extensions.md), он может иметь только статические члены.

Это предупреждение автоматически повышается до ошибки. Если вы хотите изменить это поведение, используйте [#pragma warning](../../preprocessor/warning.md).

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