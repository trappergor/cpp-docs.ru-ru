---
title: "Побочные эффекты зависимостей | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- dependencies, side effects
- NMAKE program, dependents
ms.assetid: d4e8db25-fdc0-4d73-81ec-1538f2e1b3e8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f595099d2a71c948c769adf7f7eafcbc373f3146
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="dependency-side-effects"></a>Побочные эффекты зависимостей
Если цель указана в виде двоеточия (:) в двух строках зависимостей в разных местах, и команды отображаются после только одной из строк, NMAKE интерпретирует зависимости, как если бы смежных или их комбинация. Он не вызывается правило зависимости для зависимости, которая не сопоставлены команды, а также предполагается, что зависимости принадлежат к одному блоку описания и выполняет команды, указанные для другой зависимости. Например этот набор правил:  
  
```Output  
bounce.exe : jump.obj  
   echo Building bounce.exe...  
  
bounce.exe : up.obj  
```  
  
 вычисляется как это:  
  
```Output  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
```  
  
 Этот эффект не возникает при использовании двойных кавычек (`::`) используется. Например этот набор правил:  
  
```Output  
bounce.exe :: jump.obj  
   echo Building bounce.exe...  
  
bounce.exe :: up.obj  
```  
  
 вычисляется как это:  
  
```Output  
bounce.exe : jump.obj  
   echo Building bounce.exe...  
  
bounce.exe : up.obj  
# invokes an inference rule  
```  
  
## <a name="see-also"></a>См. также  
 [Целевые объекты](../build/targets.md)