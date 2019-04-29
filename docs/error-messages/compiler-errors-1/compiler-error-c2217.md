---
title: Ошибка компилятора C2217
ms.date: 11/04/2016
f1_keywords:
- C2217
helpviewer_keywords:
- C2217
ms.assetid: 1ce1e3f5-4171-4376-804d-967f7e612935
ms.openlocfilehash: f178f969afa189910c9d23d70226ecc6c15876a4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353544"
---
# <a name="compiler-error-c2217"></a>Ошибка компилятора C2217

«атрибут1» требуется «атрибут2»

Первый атрибут функции требуется второй атрибут.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Прерывание (`__interrupt`) функция, объявленная как `near`. Прерывание функции должны быть `far`.

1. Прерывание функция, объявленная с `__stdcall`, или `__fastcall`. Функции обработки прерываний должен C использование соглашения о вызовах.

## <a name="example"></a>Пример

C2217 также может возникать при попытке привязать делегат к функцию среды CLR, которая принимает переменное число аргументов. Если функция имеет массив e param, используйте ее. Следующий пример приводит к возникновению ошибки C2217.

```
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