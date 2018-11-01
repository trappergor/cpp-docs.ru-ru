---
title: Ошибка компилятора C2201
ms.date: 11/04/2016
f1_keywords:
- C2201
helpviewer_keywords:
- C2201
ms.assetid: ed927659-6e9c-447d-9963-19969ae1e957
ms.openlocfilehash: b011c5027af6c0561010c6d11d3efd07234549f3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621604"
---
# <a name="compiler-error-c2201"></a>Ошибка компилятора C2201

«Идентификатор»: для экспорта или импорта требуется внешняя компоновка

Тип экспортируемого идентификатора — `static`.

При компиляции следующего примера возникнет ошибка C2286:

```
// C2201.cpp
// compile with: /c
__declspec(dllexport) static void func() {}   // C2201 func() is static
__declspec(dllexport) void func2() {}   // OK
```

## <a name="see-also"></a>См. также

[Типы компоновки](../../cpp/types-of-linkage.md)