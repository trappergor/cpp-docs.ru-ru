---
title: ИМЯ (C/C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- name
dev_langs:
- C++
helpviewer_keywords:
- NAME .def file statement
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc37a96e50c6cd5bae2cc60661db04f3b92d162b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715758"
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