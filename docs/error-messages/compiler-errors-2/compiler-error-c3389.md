---
title: Ошибка компилятора C3389
ms.date: 11/04/2016
f1_keywords:
- C3389
helpviewer_keywords:
- C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
ms.openlocfilehash: 6a9568f3c3be88438eae1f28e12dc780301ead0b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584305"
---
# <a name="compiler-error-c3389"></a>Ошибка компилятора C3389

> __declspec (*ключевое слово*) не может использоваться с параметром/clr: pure или/CLR: safe

## <a name="remarks"></a>Примечания

**/CLR: pure** и **/CLR: safe** параметры компилятора признаны устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017.

Объект [__declspec](../../cpp/declspec.md) подразумевает модификатор используется состояние процесса.  [/ CLR: pure](../../build/reference/clr-common-language-runtime-compilation.md) подразумевает на [appdomain](../../cpp/appdomain.md) состояния.  Поэтому при объявлении переменной с `keyword` **__declspec** модификатор и компиляции с параметром **/CLR: pure** не допускается.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3389:

```cpp
// C3389.cpp
// compile with: /clr:pure /c
__declspec(dllexport) int g2 = 0;   // C3389
```