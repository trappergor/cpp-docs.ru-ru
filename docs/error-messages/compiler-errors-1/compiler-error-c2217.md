---
title: Ошибка компилятора C2217
ms.date: 11/04/2016
f1_keywords:
- C2217
helpviewer_keywords:
- C2217
ms.assetid: 1ce1e3f5-4171-4376-804d-967f7e612935
ms.openlocfilehash: b033d95b127a45451a776cdc336ea7d2649d3716
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87209751"
---
# <a name="compiler-error-c2217"></a>Ошибка компилятора C2217

для "атрибут1" требуется "атрибут2"

Для первого атрибута функции требуется второй атрибут.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Функция interrupt ( `__interrupt` ), объявленная как `near` . Функции прерывания должны быть `far` .

1. Функция прерывания, объявленная с помощью **`__stdcall`** , или **`__fastcall`** . Функции прерывания должны использовать соглашения о вызовах C.

## <a name="example"></a>Пример

C2217 также может возникать при попытке привязки делегата к функции CLR, которая принимает переменное число аргументов. Если функция также имеет перегрузку массива e param, используйте вместо нее. Следующий пример приводит к возникновению ошибки C2217.

```cpp
// C2217.cpp
// compile with: /clr
using namespace System;
delegate void MyDel(String^, Object^, Object^, ...);   // C2217
delegate void MyDel2(String ^, array<Object ^> ^);   // OK

int main() {
   MyDel2^ wl = gcnew MyDel2(Console::WriteLine);
   array<Object ^ > ^ x = gcnew array<Object ^>(2);
   x[0] = safe_cast<Object^>(0);
   x[1] = safe_cast<Object^>(1);

   // wl("{0}, {1}", 0, 1);
   wl("{0}, {1}", x);
}
```
