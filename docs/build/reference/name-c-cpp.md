---
title: NAME (C/C++)
ms.date: 11/04/2016
f1_keywords:
- name
helpviewer_keywords:
- NAME .def file statement
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
ms.openlocfilehash: c05e82409d6b6e48390d54160e8ff23ada788d41
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50646203"
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