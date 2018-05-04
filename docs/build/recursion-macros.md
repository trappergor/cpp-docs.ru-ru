---
title: Макросы рекурсии | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, recursion macros
- recursion macros
- macros, recursion
ms.assetid: c53e5ae7-619e-46b1-bdc2-86d8c7798b1d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2759deaff6014cbba40c97f9d627baf6a800732f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="recursion-macros"></a>Макросы рекурсии
Макросы рекурсии используются для рекурсивного запуска программы NMAKE. Рекурсивные сессии наследуют макросы командной строки и переменных среды и Tools.ini сведения. Они не наследуют правила вывода, определенные в makefile или **. СУФФИКСЫ** и **. ЦЕННОЕ** спецификации. Для передачи макросов рекурсивной сессии NMAKE, задать переменную среды с НАБОРОМ, прежде чем рекурсивный вызов, определение макроса в команде для рекурсивных вызовов или определить макрос в файле Tools.ini.  
  
|Макрос|Определение|  
|-----------|----------------|  
|**СДЕЛАТЬ**|Команда, изначально использовавшаяся для вызова NMAKE.<br /><br /> Макрос $(make) разворачивается предоставляет полный путь к nmake.exe.|  
|**MAKEDIR**|Текущий каталог во время вызова NMAKE.|  
|**MAKEFLAGS**|Параметры в данный момент. Использовать в качестве `/$(MAKEFLAGS)`.  Обратите внимание, что /F не включено.|  
  
## <a name="see-also"></a>См. также  
 [Специальные макросы NMAKE](../build/special-nmake-macros.md)