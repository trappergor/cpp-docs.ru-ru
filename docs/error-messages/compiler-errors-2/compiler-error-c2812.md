---
title: Ошибка компилятора C2812
ms.date: 11/04/2016
f1_keywords:
- C2812
helpviewer_keywords:
- C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
ms.openlocfilehash: 88b071f38cf41db9c929d25ffd526b3f2b7ca468
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531824"
---
# <a name="compiler-error-c2812"></a>Ошибка компилятора C2812

> \#Импорт не поддерживается с параметром/clr: pure и/CLR: safe

## <a name="remarks"></a>Примечания

**/CLR: pure** и **/CLR: safe** параметры компилятора признаны устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017.

[директива #import](../../preprocessor/hash-import-directive-cpp.md) не поддерживается с **/CLR: pure** и **/CLR: safe** поскольку `#import` требует использования библиотек поддержки собственного компилятора.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2812.

```cpp
// C2812.cpp
// compile with: /clr:pure /c
#import "importlib.tlb"   // C2812
```