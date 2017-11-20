---
title: "-IMPORTS (ПРОГРАММА DUMPBIN) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /imports
dev_langs: C++
helpviewer_keywords:
- IMPORTS dumpbin option
- /IMPORTS dumpbin option
- -IMPORTS dumpbin option
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e395896c7f595780b1bb6b667d53d4e3eb5fa2ce
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="imports-dumpbin"></a>/IMPORTS (DUMPBIN)
```  
/IMPORTS[:file]  
```  
  
 Этот параметр отображает список библиотек DLL (оба статически компонуемые и [задержки загрузки](../../build/reference/linker-support-for-delay-loaded-dlls.md)), которые импортируются в исполняемый файл или DLL и отдельных импортированных элементов в каждом из этих библиотек DLL.  
  
 Необязательный `file` спецификации можно задать отображение imports для этой библиотеки DLL. Пример:  
  
```  
dumpbin /IMPORTS:msvcrt.dll  
```  
  
## <a name="remarks"></a>Примечания  
 Выходными этот параметр аналогичен [/EXPORTS](../../build/reference/dash-exports.md) выходных данных.  
  
 Только [/Headers](../../build/reference/headers.md) параметр программы DUMPBIN доступна для использования в файлах, созданных с помощью [/GL](../../build/reference/gl-whole-program-optimization.md) параметр компилятора.  
  
## <a name="see-also"></a>См. также  
 [Параметры DUMPBIN](../../build/reference/dumpbin-options.md)