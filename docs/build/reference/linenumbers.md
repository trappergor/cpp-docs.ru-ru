---
title: -LINENUMBERS | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /linenumbers
dev_langs:
- C++
helpviewer_keywords:
- LINENUMBERS dumpbin option
- line numbers
- -LINENUMBERS dumpbin option
- /LINENUMBERS dumpbin option
ms.assetid: 1681d582-2c2f-484e-9920-109959549055
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f9202d7f46dbd3a619e379d076db217544bd4291
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="linenumbers"></a>/LINENUMBERS
```  
/LINENUMBERS  
```  
  
## <a name="remarks"></a>Примечания  
 Этот параметр отображает номера строк COFF. Номера строк находятся в объектный файл, если она была скомпилирована в базу данных программы (/Zi), совместим с C7 (/ Z7), или только нумерация строк (/Zd). Исполняемый файл или DLL содержит COFF номера строк, если он был связан с создать отладочную информацию (/ DEBUG).  
  
 Только [/Headers](../../build/reference/headers.md) параметр программы DUMPBIN доступна для использования в файлах, созданных с помощью [/GL](../../build/reference/gl-whole-program-optimization.md) параметр компилятора.  
  
## <a name="see-also"></a>См. также  
 [Параметры DUMPBIN](../../build/reference/dumpbin-options.md)