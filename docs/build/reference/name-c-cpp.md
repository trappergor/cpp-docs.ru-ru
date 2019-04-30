---
title: NAME (C/C++)
ms.date: 11/04/2016
f1_keywords:
- name
helpviewer_keywords:
- NAME .def file statement
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
ms.openlocfilehash: d0813befc622db72e095c449794405fc5d58465b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320582"
---
# <a name="name-cc"></a>NAME (C/C++)

Указывает имя основного выходного файла.

```
NAME [application][BASE=address]
```

## <a name="remarks"></a>Примечания

Эквивалентный способ указать имя выходного файла — с помощью [/OUT](out-output-file-name.md) параметр компоновщика, а также можно задать базовый адрес — с [/BASE](base-base-address.md) параметр компоновщика. Если указаны оба, / OUT переопределяет **имя**.

При построении библиотеки DLL, имя будет отражаться только имя DLL-файла.

## <a name="see-also"></a>См. также

[Правила для операторов определения модуля](rules-for-module-definition-statements.md)
