---
title: Ошибка компилятора C2434
ms.date: 11/04/2016
f1_keywords:
- C2434
helpviewer_keywords:
- C2434
ms.assetid: 01329e26-7c74-4219-b74f-69e3a40c9738
ms.openlocfilehash: c73a8d4fcde945ddf2495cc2d0d7dc47216f2db3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587594"
---
# <a name="compiler-error-c2434"></a>Ошибка компилятора C2434

> "*символ*": символ, объявленный с параметром __declspec(process), невозможно динамически инициализировать в/CLR: pure режим

## <a name="remarks"></a>Примечания

**/CLR: pure** и **/CLR: safe** параметры компилятора признаны устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017.

Невозможно динамически инициализировать переменную на уровне процесса, в разделе **/CLR: pure**. Дополнительные сведения см. в разделе [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) и [процесс](../../cpp/process.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2434. Чтобы устранить эту проблему, используйте константы для инициализации `process` переменные.

```cpp
// C2434.cpp
// compile with: /clr:pure /c
int f() { return 0; }
__declspec(process) int i = f();   // C2434
__declspec(process) int i2 = 0;   // OK
```