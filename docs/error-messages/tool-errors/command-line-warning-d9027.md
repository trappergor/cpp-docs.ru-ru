---
title: Предупреждение командной строки D9027 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9027
dev_langs:
- C++
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dfe2493290c4e4cc5b744136b8e7036c6559220a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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