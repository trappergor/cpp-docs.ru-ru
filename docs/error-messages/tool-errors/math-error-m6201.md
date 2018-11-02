---
title: Математическая ошибка M6201
ms.date: 11/04/2016
f1_keywords:
- M6201
helpviewer_keywords:
- M6201
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
ms.openlocfilehash: 6d3f107de7e45653374036ecafaa864cb3eff5b0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622109"
---
# <a name="math-error-m6201"></a>Математическая ошибка M6201

«функция»: ошибка _доменное

Аргумент для данной функции находится вне домена допустимых входных значений для этой функции.

## <a name="example"></a>Пример

```
result = sqrt(-1.0)   // C statement
result = SQRT(-1.0)   !  FORTRAN statement
```

Эта ошибка вызывает `_matherr` функцию с именем функции, аргументы и тип ошибки. Можно переписать `_matherr` функции для обработки определенных ошибок времени выполнения вычисления с плавающей запятой.