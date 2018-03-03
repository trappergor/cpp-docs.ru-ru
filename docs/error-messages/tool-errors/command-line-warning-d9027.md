---
title: "Предупреждение командной строки D9027 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- D9027
dev_langs:
- C++
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2769eb5f78cb1d5bdd6749e65429d83b69a2807b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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