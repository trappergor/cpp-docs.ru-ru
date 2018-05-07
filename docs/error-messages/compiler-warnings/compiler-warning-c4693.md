---
title: Предупреждение компилятора C4693 | Документы Microsoft
ms.date: 10/25/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4693
dev_langs:
- C++
helpviewer_keywords:
- C4693
ms.assetid: 72d8db01-5e6f-4794-8731-76107e8f064a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f8230e60d65c80b4f839cc8a1c97ccc0c7b18086
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-c4693"></a>Предупреждение компилятора C4693

> "класс": у запечатанного абстрактного класса не может быть членов экземпляра "Тест"

Если тип помечен [запечатанный](../../windows/sealed-cpp-component-extensions.md) и [абстрактный](../../windows/abstract-cpp-component-extensions.md), он может содержать только статические члены.

Это предупреждение автоматически повышается до ошибки. Если вы хотите изменить такое поведение, используйте [#pragma warning](../../preprocessor/warning.md).

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