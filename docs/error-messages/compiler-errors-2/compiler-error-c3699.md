---
title: Ошибка компилятора C3699
ms.date: 11/04/2016
f1_keywords:
- C3699
helpviewer_keywords:
- C3699
ms.assetid: 47c29afc-ab8b-4238-adfe-788dd6e00b3b
ms.openlocfilehash: 93058d34ca9a17ab175a55a7bc7b953d369e65c5
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59779457"
---
# <a name="compiler-error-c3699"></a>Ошибка компилятора C3699

«operator»: нельзя использовать перенаправление для типа «тип»

Была предпринята попытка использовать косвенного обращения, не разрешена для `type`.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3699.

```
// C3699.cpp
// compile with: /clr /c
using namespace System;
int main() {
   String * s;   // C3699
   // try the following line instead
   // String ^ s2;
}
```

## <a name="example"></a>Пример

Тривиальное свойство не может иметь ссылочный тип. Дополнительные сведения см. в разделе [property](../../extensions/property-cpp-component-extensions.md) . Следующий пример приводит к возникновению ошибки C3699.

```
// C3699_b.cpp
// compile with: /clr /c
ref struct C {
   property System::String % x;   // C3699
   property System::String ^ y;   // OK
};
```

## <a name="example"></a>Пример

Эквивалент синтаксиса «указатель на указатель» является дескриптором для отслеживания ссылок. Следующий пример приводит к возникновению ошибки C3699.

```
// C3699_c.cpp
// compile with: /clr /c
using namespace System;
void Test(String ^^ i);   // C3699
void Test2(String ^% i);
```