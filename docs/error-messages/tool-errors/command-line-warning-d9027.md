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
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 7d569243a6d0d1669a8964ab9c419cb0e7428ba9
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="command-line-warning-d9027"></a>Предупреждение командной строки D9027
исходный файл "\<имя файла настроек" игнорируется  
  
 CL.exe учитывается входного исходного файла.  
  
 Это предупреждение может быть вызвано пробел между параметром /Fo и именем выходного файла в командной строке с параметром. Например:  
  
```  
cl /c /Fo output.obj input.c   
```  
  
 Так как отсутствует пробел между /Fo и `output.obj`, принимает CL.exe `output.obj` как имя входного файла. Чтобы исправить эту проблему, удалите пространство:  
  
```  
cl /c /Fooutput.obj input.c   
```
