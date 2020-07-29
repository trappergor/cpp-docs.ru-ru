---
title: Математическая ошибка M6111
ms.date: 11/04/2016
f1_keywords:
- M6111
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
ms.openlocfilehash: 986c0e53edcddfc47eb9ba970f3c32385e0a57d9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225193"
---
# <a name="math-error-m6111"></a>Математическая ошибка M6111

потеря значимости стека

Операция с плавающей запятой привела к незначимости стека на сопроцессоре 8087/287/387 или в эмуляторе.

Эта ошибка часто возникает из-за вызова **`long double`** функции, которая не возвращает значение. Например, следующая ошибка возникает при компиляции и выполнении:

```
long double ld() {};
main ()
{
  ld();
}
```

Программа завершается с кодом выхода 139.
