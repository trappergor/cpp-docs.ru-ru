---
title: "Предупреждение средств компоновщика LNK4105 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4105
dev_langs: C++
helpviewer_keywords: LNK4105
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 913a6da056908def8df5aab1c2425ef9a187c1e2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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