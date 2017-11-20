---
title: "-APPCONTAINER | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /APPCONTAINER
dev_langs: C++
helpviewer_keywords:
- APPCONTAINER editbin option
- -APPCONTAINER editbin option
- /APPCONTAINER editbin option
ms.assetid: 0ca4f1ec-c8de-4a37-b3e2-deda7af0bb88
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 62b23ed04783971bf37442237e4db770b7427a8d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="appcontainer"></a>/APPCONTAINER
Помечает исполняемый файл, который должен выполняться в контейнере приложения, например [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] или универсальное приложение Windows.  
  
```  
  
/APPCONTAINER[:NO]  
```  
  
## <a name="remarks"></a>Примечания  
 Исполняемый файл, для которого задан параметр **/APPCONTAINER** , может выполняться только в контейнере приложения, то есть в среде изоляции процессов, которая была введена в Windows 8. Для [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] и универсальных приложений Windows этот параметр должен быть установлен.  
  
## <a name="see-also"></a>См. также  
 [Параметры EDITBIN](../../build/reference/editbin-options.md)   
 [Что такое универсальное приложение Windows?](http://go.microsoft.com/fwlink/p/?LinkID=522074)