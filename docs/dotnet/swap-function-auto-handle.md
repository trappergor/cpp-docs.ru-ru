---
title: Функция swap (auto_handle)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msclr::swap
- msclr.swap
helpviewer_keywords:
- swap function
ms.assetid: 7dd91b5c-f0de-4634-a2e2-642626706e27
ms.openlocfilehash: a4e15e2a0481f10b58517135c5dc283549f358af
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638306"
---
# <a name="swap-function-autohandle"></a>Функция swap (auto_handle)

Меняет местами объекты между одним `auto_handle` и другого.

## <a name="syntax"></a>Синтаксис

```
template<typename _element_type>
void swap(
   auto_handle<_element_type> % _left,
   auto_handle<_element_type> % _right
);
```

#### <a name="parameters"></a>Параметры

*_слева*<br/>
Объект `auto_handle`.

*_справа*<br/>
Другой `auto_handle`.

## <a name="example"></a>Пример

```
// msl_swap_auto_handle.cpp
// compile with: /clr
#include <msclr\auto_handle.h>

using namespace System;
using namespace msclr;

int main() {
   auto_handle<String> s1 = "string one";
   auto_handle<String> s2 = "string two";

   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",
      s1->ToString(), s2->ToString() );
   swap( s1, s2 );
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",
      s1->ToString(), s2->ToString() );
}
```

```Output
s1 = 'string one', s2 = 'string two'
s1 = 'string two', s2 = 'string one'
```

## <a name="requirements"></a>Требования

**Файл заголовка** \<msclr\auto_handle.h >

**Пространство имен** msclr

## <a name="see-also"></a>См. также

[auto_handle](../dotnet/auto-handle.md)<br/>
[auto_handle::swap](../dotnet/auto-handle-swap.md)