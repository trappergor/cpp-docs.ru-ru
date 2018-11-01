---
title: Ошибка компилятора C2393
ms.date: 11/04/2016
f1_keywords:
- C2393
helpviewer_keywords:
- C2393
ms.assetid: 4bd95728-e813-4ce8-844a-c6ebe235ca82
ms.openlocfilehash: 39ca693aed3f08e7b2df3d687f94d93384393f23
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566859"
---
# <a name="compiler-error-c2393"></a>Ошибка компилятора C2393

> "*символ*": символ по доменам приложения не может быть помещен в сегмент "*сегмент*"

## <a name="remarks"></a>Примечания

**/CLR: pure** и **/CLR: safe** параметры компилятора признаны устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017.

Использование [appdomain](../../cpp/appdomain.md) переменные подразумевает, что при компиляции с **/CLR: pure** или **/CLR: safe**, и образ safe или pure не может содержать сегменты данных.

См. в разделе [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) Дополнительные сведения.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2393. Чтобы устранить эту проблему, не создавайте сегмента данных.

```cpp
// C2393.cpp
// compile with: /clr:pure /c
#pragma data_seg("myseg")
int n = 0;   // C2393
```