---
title: "Предупреждение командной строки D9027 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: D9027
dev_langs: C++
helpviewer_keywords: D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5ccdccbc4c6df8f948b44eeaa096cff46824d043
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="command-line-warning-d9027"></a>Предупреждение командной строки D9027
исходный файл "\<имя_файла >" игнорируется  
  
 CL.exe учитывается входного исходного файла.  
  
 Это предупреждение может быть вызвано пробел между параметром /Fo и именем выходного файла в командной строке с параметром. Пример:  
  
```  
cl /c /Fo output.obj input.c   
```  
  
 Так как отсутствует пробел между /Fo и `output.obj`, принимает CL.exe `output.obj` как имя входного файла. Чтобы исправить эту проблему, удалите пространство:  
  
```  
cl /c /Fooutput.obj input.c   
```