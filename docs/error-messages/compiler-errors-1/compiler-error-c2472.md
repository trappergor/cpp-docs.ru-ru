---
title: Ошибка компилятора C2472 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2472
dev_langs:
- C++
helpviewer_keywords:
- C2472
ms.assetid: 3b36bcdc-2ba5-4357-ab88-7545ba0551cd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 43279190847322fa2154c6faababdcd41b490eef
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704864"
---
# <a name="compiler-error-c2472"></a>Ошибка компилятора C2472

> "*функция*" не может создаваться в управляемом коде: "*сообщение*"; Компиляция с параметром/CLR для генерации смешанного образа

## <a name="remarks"></a>Примечания

Эта ошибка возникает при использовании типов, не поддерживаемых в управляемом коде, в чистой среде CLR. Для устранения этой ошибки выполните компиляцию с параметром **/clr** .

**/CLR: pure** и **/CLR: safe** параметры компилятора являются устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017 г.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2472:

```cpp
// C2472.cpp
// compile with: /clr:pure
// C2472 expected

#include <cstdlib>

int main()
{
   int * __ptr32 p32;
   int * __ptr64 p64;

   p32 = (int * __ptr32)malloc(4);
   p64 = p32;
}
```

## <a name="see-also"></a>См. также

- [/clr (компиляция среды выполнения)](../../build/reference/clr-common-language-runtime-compilation.md)
