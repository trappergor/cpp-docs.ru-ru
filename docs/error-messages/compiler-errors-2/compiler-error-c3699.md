---
title: Ошибка компилятора C3699 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3699
dev_langs:
- C++
helpviewer_keywords:
- C3699
ms.assetid: 47c29afc-ab8b-4238-adfe-788dd6e00b3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 64e5a5bb98f9e8a6950bbb279c026f167a2ee92e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46107720"
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

Тривиальное свойство не может иметь ссылочный тип. Дополнительные сведения см. в разделе [property](../../windows/property-cpp-component-extensions.md) . Следующий пример приводит к возникновению ошибки C3699.

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