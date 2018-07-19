---
title: -RAWDATA | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28691e636f01174ecfe2a9d48b016523fce67f14
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375003"
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