---
title: Ошибка компилятора C3862 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3862
dev_langs:
- C++
helpviewer_keywords:
- C3862
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5b21e457feb6d090e4abaf531293987eb3504457
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704975"
---
# <a name="compiler-error-c3862"></a>Ошибка компилятора C3862

> "*функция*": не удается скомпилировать неуправляемую функцию с параметром/clr: pure или/CLR: safe

## <a name="remarks"></a>Примечания

**/CLR: pure** и **/CLR: safe** параметры компилятора являются устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017 г.

Компиляция с **/CLR: pure** или **/CLR: safe** может дать только изображение MSIL, изображение с без машинного (неуправляемого) кода.  Следовательно, нельзя использовать `unmanaged` pragma в **/CLR: pure** или **/CLR: safe** компиляции.

Дополнительные сведения см. в разделе [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) и [управляемые, неуправляемые](../../preprocessor/managed-unmanaged.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3862:

```cpp
// C3862.cpp
// compile with: /clr:pure /c
#pragma unmanaged
void f() {}   // C3862
```