---
title: FpCsr | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: dff95d5d-7589-4432-82db-64b459c24352
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6ed0500d0382563878d0751ba5386e4cc637fdb
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718293"
---
# <a name="fpcsr"></a>FpCsr

Состояние регистра также включает в себя x87 контрольного слова FPU. Соглашение о вызове определяет этот регистр должен быть неизменным.

Выполнение программы x87 присваиваемого регистру контрольного слова FPU следующие стандартные значения в начале:

```
FPCSR[0:6]: Exception masks all 1's (all exceptions masked)
FPCSR[7]: Reserved - 0
FPCSR[8:9]: Precision Control - 10B (double precision)
FPCSR[10:11]: Rounding  control - 0 (round to nearest)
FPCSR[12]: Infinity control - 0 (not used)
```

Вызываемый объект, который изменяет любое из полей в FPCSR необходимо восстановить их, прежде чем возвращать его вызывающему. Более того вызывающий объект, который был изменен любой из этих полей, должен восстановить их стандартные значения перед вызовом вызываемым объектом, если только соглашением вызываемый требует измененные значения.

Существует два исключения из правил с учетом неизменяемости управляющих флагов.

1. В функциях, где документированных заданная функция предназначена для изменения защищенных FpCsr флаги.

1. Когда это вероятно так, что нарушения этих правил приводит к созданию программы, поведение так же, как программы, где эти правила не нарушены, например, посредством анализа всей программы.

## <a name="see-also"></a>См. также

[Соглашение о вызовах](../build/calling-convention.md)