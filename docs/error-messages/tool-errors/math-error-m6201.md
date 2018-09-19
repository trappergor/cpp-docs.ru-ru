---
title: Математическая ошибка M6201 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6201
dev_langs:
- C++
helpviewer_keywords:
- M6201
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 87d2c09d6448bcf7fb0557fa3a174c60205a34ea
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099399"
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