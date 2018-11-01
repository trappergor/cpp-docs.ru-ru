---
title: Ошибка компилятора C2158
ms.date: 11/04/2016
f1_keywords:
- C2158
helpviewer_keywords:
- C2158
ms.assetid: 39028899-e95c-4809-8e65-6111118641ee
ms.openlocfilehash: a84c803d45184c19bab0f855ae1eb33744c4e02d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597396"
---
# <a name="compiler-error-c2158"></a>Ошибка компилятора C2158

"тип": директива #pragma make_public сейчас поддерживается только для собственных нешаблонных типов

Директива pragma [make_public](../../preprocessor/make-public.md) может применяться только к собственным нешаблонным типам.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2158:

```
// C2158.cpp
// compile with: /clr /c
ref class A {};
#pragma make_public(A)   // C2158

template< typename T >
class B {};
#pragma make_public(B)   // C2158
#pragma make_public(B<int>)   // C2158

void C () {}
#pragma make_public(C)   // C2158

class D {};
#pragma make_public(D)   // OK
```