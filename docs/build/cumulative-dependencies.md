---
title: "Кумулятивные зависимости | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- dependencies, cumulative
- cumulative dependencies in NMAKE
- dependencies
ms.assetid: fa6dd777-80b8-437d-87a7-aec0ed818a49
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f2fd356ae37eda8820e3a6e0e31a8cecde8d3929
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cumulative-dependencies"></a>Кумулятивные зависимости
Зависимости являются кумулятивными в блоке описания, если целевой объект повторяется.  
  
 Например этот набор правил,  
  
```Output  
bounce.exe : jump.obj  
bounce.exe : up.obj  
   echo Building bounce.exe...  
```  
  
 вычисляется как это:  
  
```Output  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
```  
  
 Целевые объекты в нескольких строках зависимостей одного блока описания оцениваются, как если бы каждый объект был указан в отдельном блоке описания, но целевые объекты, которые не находятся в последней строке зависимости следует использовать блок команд. NMAKE предпринимает попытку использовать правила вывода для таких целей.  
  
 Например этот набор правил,  
  
```Output  
leap.exe bounce.exe : jump.obj  
bounce.exe climb.exe : up.obj  
   echo Building bounce.exe...  
```  
  
 вычисляется как это:  
  
```Output  
  
leap.exe : jump.obj  
# invokes an inference rule  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
climb.exe : up.obj  
   echo Building bounce.exe...  
```  
  
## <a name="see-also"></a>См. также  
 [Целевые объекты](../build/targets.md)