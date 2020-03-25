---
title: Математическая ошибка M6111
ms.date: 11/04/2016
f1_keywords:
- M6111
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
ms.openlocfilehash: e8abedf6a326a826d0c8ac513b15037c8bf89bce
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80173695"
---
# <a name="math-error-m6111"></a>Математическая ошибка M6111

потеря значимости стека

Операция с плавающей запятой привела к незначимости стека на сопроцессоре 8087/287/387 или в эмуляторе.

Эта ошибка часто возникает из-за вызова функции `long double`, которая не возвращает значение. Например, следующая ошибка возникает при компиляции и выполнении:

```
long double ld() {};
main ()
{
  ld();
}
```

Программа завершается с кодом выхода 139.
