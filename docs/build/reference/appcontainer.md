---
title: -APPCONTAINER | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /APPCONTAINER
dev_langs:
- C++
helpviewer_keywords:
- APPCONTAINER editbin option
- -APPCONTAINER editbin option
- /APPCONTAINER editbin option
ms.assetid: 0ca4f1ec-c8de-4a37-b3e2-deda7af0bb88
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5c47154d7a5eddd26573612708462c0352da30ae
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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