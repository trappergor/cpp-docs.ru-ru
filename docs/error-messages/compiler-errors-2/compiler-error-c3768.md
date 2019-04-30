---
title: Ошибка компилятора C3768
ms.date: 11/04/2016
f1_keywords:
- C3768
helpviewer_keywords:
- C3768
ms.assetid: 091f0d53-1dff-43fd-813d-5c43c85b6ab0
ms.openlocfilehash: e9c385fd178dc967e72f5e0ca7fab27b28ad962f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400218"
---
# <a name="compiler-error-c3768"></a>Ошибка компилятора C3768

> Невозможно получить адрес функции виртуального vararg в полностью управляемого кода

## <a name="remarks"></a>Примечания

**/CLR: pure** параметр компилятора в Visual Studio 2015 не рекомендуется и не поддерживается в Visual Studio 2017.

При компиляции с параметром **/CLR: pure**, невозможно получить адрес виртуальной `vararg` функции.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3768:

```cpp
// C3768.cpp
// compile with: /clr:pure
struct A
{
   virtual void f(...);
};

int main()
{
   &(A::f);   // C3768
}
```