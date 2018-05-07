---
title: Предупреждение командной строки D9026 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9026
dev_langs:
- C++
helpviewer_keywords:
- D9026
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9e2d99573ee46c51178cc2fe995fa0f526b800f9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="command-line-warning-d9026"></a>Предупреждение командной строки D9026
параметры применяются ко всей командной строке  
  
 Параметр был указан в команде, после определения имени файла. Параметр был применен к файлу, расположенному перед ним.  
  
 Например в команде  
  
```  
CL verdi.c /G5 puccini.c  
```  
  
 файл VERDI.c будет компилироваться с помощью параметра/G5, а не/G4 по умолчанию.  
  
 Это поведение отличается от некоторых предыдущих версий, которые применяли только параметры, указанные перед именем файла, что приводит к VERDI.c с помощью/G4, а PUCCINI.c компилируется с помощью/G5.