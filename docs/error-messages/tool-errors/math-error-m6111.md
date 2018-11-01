---
title: Математическая ошибка M6111
ms.date: 11/04/2016
f1_keywords:
- M6111
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
ms.openlocfilehash: 44f406881d64d13e23ca2c0911ee278c864a2c11
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50510790"
---
# <a name="math-error-m6111"></a>Математическая ошибка M6111

потеря значимости в стеке

Операции с плавающей запятой привело к нижнюю границу стек на 8087/287/387 или эмуляторе.

Эта ошибка часто возникает при вызове `long double` функцию, которая не возвращает значение. Например ниже создает эту ошибку при компиляции и выполнения:

```
long double ld() {};
main ()
{
  ld();
}
```

Программа завершается с кодом завершения 139.