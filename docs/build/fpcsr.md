---
title: FpCsr | Документы Microsoft
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
ms.openlocfilehash: 9defb41a026b32acb4375185f14c903788b91a23
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="fpcsr"></a>FpCsr
Состояние регистра включает x87 контрольного слова FPU. Определяет соглашение о вызовах, этот регистр должен быть неизменным.  
  
 X87 присваиваемого регистру контрольного слова FPU следующие стандартные значения в начале выполнения программы:  
  
```  
FPCSR[0:6]: Exception masks all 1's (all exceptions masked)  
FPCSR[7]: Reserved - 0  
FPCSR[8:9]: Precision Control - 10B (double precision)  
FPCSR[10:11]: Rounding  control - 0 (round to nearest)  
FPCSR[12]: Infinity control - 0 (not used)  
```  
  
 Вызываемый объект, который изменяет любое из полей в FPCSR необходимо восстановить его до возвращения вызывающему. Кроме того вызывающий объект, который был изменен любой из этих полей должен восстановить их стандартные значения до вызова функции или процедуры, если соглашением вызываемый требует, чтобы измененные значения.  
  
 Существует два исключения из правил с учетом неизменяемости управляющих флагов.  
  
1.  В функциях, где документированные заданной функции предназначена для изменения защищенных FpCsr флагов.  
  
2.  При его правильности вероятно, нарушение этих правил приведет к созданию программы, поведение таким же, как программы, где эти правила не нарушены, например, посредством анализа всей программы.  
  
## <a name="see-also"></a>См. также  
 [Соглашение о вызовах](../build/calling-convention.md)