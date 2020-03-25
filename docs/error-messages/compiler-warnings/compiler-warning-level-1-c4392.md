---
title: Предупреждение компилятора (уровень 1) C4392
ms.date: 11/04/2016
f1_keywords:
- C4392
helpviewer_keywords:
- C4392
ms.assetid: 817806ad-06a6-4b9e-8355-e25687c782dc
ms.openlocfilehash: a62bfdb6b9b29abf047e7690179978cb9516d477
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186885"
---
# <a name="compiler-warning-level-1-c4392"></a>Предупреждение компилятора (уровень 1) C4392

"сигнатура": неправильное число аргументов для подставляемой функции; требуется аргументов: "число"

Объявление функции для встроенного компилятора имело неверное число аргументов. Полученный образ может работать неправильно.

Чтобы устранить это предупреждение, исправьте объявление или удалите объявление и просто #include соответствующий файл заголовка.

Следующий пример приводит к возникновению ошибки C4392:

```cpp
// C4392.cpp
// compile with: /W1
// processor: x86
// uncomment the following line and delete the line that
// generated the warning to resolve
// #include "xmmintrin.h"

#ifdef  __cplusplus
extern "C" {
#endif

extern void _mm_stream_pd(double *dp);   // C4392

#ifdef  __cplusplus
}
#endif

int main()
{
}
```
