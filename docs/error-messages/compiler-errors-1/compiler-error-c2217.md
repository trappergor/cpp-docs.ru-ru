---
title: Ошибка компилятора C2217 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2217
dev_langs:
- C++
helpviewer_keywords:
- C2217
ms.assetid: 1ce1e3f5-4171-4376-804d-967f7e612935
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a4eb8b9fcaffa30f3a5ced5362a0f9d54a45f07e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050623"
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