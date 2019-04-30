---
title: Ошибка компилятора C3738
ms.date: 11/04/2016
f1_keywords:
- C3738
helpviewer_keywords:
- C3738
ms.assetid: dd3ee011-e204-4264-bf3a-da32c4ef7038
ms.openlocfilehash: e313c7d66bc030183e330dd961fad2fb35f02ac2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327812"
---
# <a name="compiler-error-c3738"></a>Ошибка компилятора C3738

«соглашение_о_вызовах»: соглашение о вызове явном создании экземпляров должно совпадать со значением шаблона создаваемых экземпляров

Рекомендуется, что не нужно указывать соглашение о вызовах в явном создании экземпляра. Если вам необходимо, то должно соответствовать соглашения о вызовах.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3738.

```
// C3738.cpp
// compile with: /clr
// processor: x86
#include <stdio.h>
template< class T >
void f ( T arg ) {   // by default calling convention is __cdecl
   printf ( "f: %s\n", __FUNCSIG__ );
}

template
void __stdcall f< int > ( int arg );   // C3738
// try the following line instead
// void f< int > ( int arg );

int main () {
   f(1);
   f< int > ( 1 );
}
```