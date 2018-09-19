---
title: Ошибка компилятора C3738 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3738
dev_langs:
- C++
helpviewer_keywords:
- C3738
ms.assetid: dd3ee011-e204-4264-bf3a-da32c4ef7038
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 07a71ae25f62d50ec52860e61e195f1c19f78030
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096565"
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