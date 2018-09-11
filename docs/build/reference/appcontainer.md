---
title: -APPCONTAINER | Документация Майкрософт
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
ms.openlocfilehash: ea6f08a141d48183d96dba6cb02fcf31909af0ae
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43686257"
---
# <a name="appcontainer"></a>/APPCONTAINER
Помечает исполняемый файл, который должен выполняться в контейнере приложения — например, Microsoft Store или универсальной Windows приложение.  
  
```  
  
/APPCONTAINER[:NO]  
```  
  
## <a name="remarks"></a>Примечания  
 Исполняемый файл, для которого задан параметр **/APPCONTAINER** , может выполняться только в контейнере приложения, то есть в среде изоляции процессов, которая была введена в Windows 8. Для приложений Microsoft Store и универсальной Windows этот параметр должен быть установлен.  
  
## <a name="see-also"></a>См. также  
 [Параметры EDITBIN](../../build/reference/editbin-options.md)   
 [Что такое приложение универсальной Windows?](/windows/uwp/get-started/universal-application-platform-guide)