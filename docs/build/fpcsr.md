---
title: FpCsr | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: dff95d5d-7589-4432-82db-64b459c24352
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 15b7caebc99c4724c0e28b7812da8ef224184385
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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