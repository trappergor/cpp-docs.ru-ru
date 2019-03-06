---
title: NAME (C/C++)
ms.date: 11/04/2016
f1_keywords:
- name
helpviewer_keywords:
- NAME .def file statement
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
ms.openlocfilehash: c4888b8f9b6dba4b826f2ee7dda7529a4bdf1586
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57414503"
---
# <a name="name-cc"></a>NAME (C/C++)

Указывает имя основного выходного файла.

```
NAME [application][BASE=address]
```

## <a name="remarks"></a>Примечания

Эквивалентный способ указать имя выходного файла — с помощью [/OUT](../../build/reference/out-output-file-name.md) параметр компоновщика, а также можно задать базовый адрес — с [/BASE](../../build/reference/base-base-address.md) параметр компоновщика. Если указаны оба, / OUT переопределяет **имя**.

При построении библиотеки DLL, имя будет отражаться только имя DLL-файла.

## <a name="see-also"></a>См. также

[Правила для операторов определения модуля](../../build/reference/rules-for-module-definition-statements.md)
