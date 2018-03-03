---
title: "Предупреждение командной строки D9026 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- D9026
dev_langs:
- C++
helpviewer_keywords:
- D9026
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9127ad1887d476e5460798f806c2db1ff3144de3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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