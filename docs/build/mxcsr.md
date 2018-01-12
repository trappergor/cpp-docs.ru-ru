---
title: "MxCsr | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 4f3c229d-0862-4733-acc7-9ed7a0b870ce
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7794cea8906440c0adca94791d08e3ced6af747e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="mxcsr"></a>Регистр MxCsr
Состояние регистра включает MxCsr. Соглашение о вызове разделяет регистр volatile часть и защищенную. Изменяемая часть состоит из 6 флагов состояния, MXCSR [0:5], а остальная часть регистр MXCSR [6:15] считается энергонезависимого.  
  
 Для защищенной части задано следующие стандартные значения в начале выполнения программы:  
  
```  
MXCSR[6]         : Denormals are zeros - 0  
MXCSR[7:12]      : Exception masks all 1's (all exceptions masked)  
MXCSR[13:14]   : Rounding  control - 0 (round to nearest)  
MXCSR[15]      : Flush to zero for masked underflow - 0 (off)  
```  
  
 Вызываемый объект, который изменяет любое из защищенных полей в MXCSR необходимо восстановить его до возвращения вызывающему. Кроме того вызывающий объект, который был изменен любой из этих полей должен восстановить их стандартные значения до вызова функции или процедуры, если соглашением вызываемый требует, чтобы измененные значения.  
  
 Существует два исключения из правил с учетом неизменяемости управляющих флагов.  
  
-   В функциях, где документированные заданной функции предназначена для изменения защищенных MxCsr флагов.  
  
-   При его правильности вероятно, нарушение этих правил приведет к созданию программы, поведение таким же, как программы, где эти правила не нарушены, например, посредством анализа всей программы.  
  
 Можно сделать никаких предположений о состоянии volatile части MXCSR на границе функции оговорено особо в документации функции.  
  
## <a name="see-also"></a>См. также  
 [Соглашение о вызовах](../build/calling-convention.md)