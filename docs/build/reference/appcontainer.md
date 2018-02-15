---
title: "-APPCONTAINER | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /APPCONTAINER
dev_langs:
- C++
helpviewer_keywords:
- APPCONTAINER editbin option
- -APPCONTAINER editbin option
- /APPCONTAINER editbin option
ms.assetid: 0ca4f1ec-c8de-4a37-b3e2-deda7af0bb88
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 08966cd2b9da434c45750edb57644c182a14baf2
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="appcontainer"></a>/APPCONTAINER
Помечает исполняемый файл, необходимо запустить в контейнере приложения, например, Microsoft Store или универсальных приложений Windows приложения.  
  
```  
  
/APPCONTAINER[:NO]  
```  
  
## <a name="remarks"></a>Примечания  
 Исполняемый файл, для которого задан параметр **/APPCONTAINER** , может выполняться только в контейнере приложения, то есть в среде изоляции процессов, которая была введена в Windows 8. Этот параметр должен быть установлен для приложений Microsoft Store и универсальных приложений Windows.  
  
## <a name="see-also"></a>См. также  
 [Параметры EDITBIN](../../build/reference/editbin-options.md)   
 [Что такое универсальное приложение Windows?](http://go.microsoft.com/fwlink/p/?LinkID=522074)