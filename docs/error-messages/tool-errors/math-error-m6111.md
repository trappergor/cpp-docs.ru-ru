---
title: Математическая ошибка M6111 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6111
dev_langs:
- C++
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 95a55ec6b7cdf0b6e4c15bd283dde77c610698fa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074829"
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