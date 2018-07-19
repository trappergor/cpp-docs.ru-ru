---
title: -IMPORTS (ПРОГРАММА DUMPBIN) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /imports
dev_langs:
- C++
helpviewer_keywords:
- IMPORTS dumpbin option
- /IMPORTS dumpbin option
- -IMPORTS dumpbin option
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af3b9a1bbcf1769e87715e46566dee9c53a96747
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373443"
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