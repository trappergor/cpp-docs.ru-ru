---
title: "-RAWDATA | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /rawdata
dev_langs:
- C++
helpviewer_keywords:
- RAWDATA dumpbin option
- raw data
- -RAWDATA dumpbin option
- /RAWDATA dumpbin option
ms.assetid: 41cba845-5e1f-415e-9fe4-604a52235983
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 475ec5a827a1453a6f9474762d5be41299fc87e4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="rawdata"></a>/RAWDATA
```  
/RAWDATA[:{1|2|4|8|NONE[,number]]  
```  
  
## <a name="remarks"></a>Примечания  
 Этот параметр отображает необработанное содержимое каждого раздела в файле. Аргументы определяют формат отображения, как показано ниже:  
  
|Аргумент|Результат|  
|--------------|------------|  
|1|По умолчанию. Содержимое отображается в шестнадцатеричных байтов, а также как знаки ASCII, если они имеют печатной представление.|  
|2|Содержимое отображаются в виде шестнадцатеричных значений длиной 2 байта.|  
|4|Содержимое отображаются в виде шестнадцатеричных значений 4 байта.|  
|8|Содержимое отображаются в виде шестнадцатеричных значений размером 8 байт.|  
|НЕТ|Необработанные данные отбрасываются. Этот аргумент полезен для управления выводом/ALL.|  
|*Число*|Отображенные строки устанавливаются по ширине, который содержит `number` значений для каждой строки.|  
  
 Только [/Headers](../../build/reference/headers.md) параметр программы DUMPBIN доступна для использования в файлах, созданных с помощью [/GL](../../build/reference/gl-whole-program-optimization.md) параметр компилятора.  
  
## <a name="see-also"></a>См. также  
 [Параметры DUMPBIN](../../build/reference/dumpbin-options.md)