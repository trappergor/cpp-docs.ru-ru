---
title: Предупреждение средств компоновщика LNK4105 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4105
dev_langs:
- C++
helpviewer_keywords:
- LNK4105
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ffdd8953e08f38d36bdfc2e68ad6cb8e06fb85b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4105"></a>Предупреждение средств компоновщика LNK4105
не указаны аргументы параметра «параметр»; параметр игнорируется  
  
 Это предупреждение возникает только при [/LIBPATH](../../build/reference/libpath-additional-libpath.md) был установлен. Если каталог не указан этот параметр, компоновщик игнорирует параметр и создает для этого предупреждения.  
  
 Если не требуется переопределять существующие настройки библиотеки среды, удалите параметр/LIBPATH из командной строки компоновщика. Если вы хотите использовать поиска альтернативный путь для библиотек, укажите альтернативный путь после параметра/LIBPATH.  
  
## <a name="example"></a>Пример  
  
```  
link /libpath:c:\filepath\lib bar.obj  
```  
  
 компоновщиком для поиска необходимых библиотек в `c:\filepath\lib` до выполнения поиска в расположение по умолчанию.