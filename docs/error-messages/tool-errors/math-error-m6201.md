---
title: Математическая ошибка M6201
ms.date: 11/04/2016
f1_keywords:
- M6201
helpviewer_keywords:
- M6201
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
ms.openlocfilehash: 6d3f107de7e45653374036ecafaa864cb3eff5b0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393250"
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