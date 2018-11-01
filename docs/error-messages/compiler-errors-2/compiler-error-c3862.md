---
title: Ошибка компилятора C3862
ms.date: 11/04/2016
f1_keywords:
- C3862
helpviewer_keywords:
- C3862
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
ms.openlocfilehash: 2ba130862b1debbe2991ca7cbcae50192f900cd8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50446245"
---
# <a name="compiler-error-c3862"></a>Ошибка компилятора C3862

> "*функция*": не удается скомпилировать неуправляемую функцию с параметром/clr: pure или/CLR: safe

## <a name="remarks"></a>Примечания

**/CLR: pure** и **/CLR: safe** параметры компилятора признаны устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017.

В компиляцию с параметром **/CLR: pure** или **/CLR: safe** может дать только изображение MSIL, изображение без машинного (неуправляемого) кода.  Следовательно, нельзя использовать `unmanaged` прагма-директиву **/CLR: pure** или **/CLR: safe** компиляции.

Дополнительные сведения см. в разделе [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) и [управляемые, неуправляемые](../../preprocessor/managed-unmanaged.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3862:

```cpp
// C3862.cpp
// compile with: /clr:pure /c
#pragma unmanaged
void f() {}   // C3862
```