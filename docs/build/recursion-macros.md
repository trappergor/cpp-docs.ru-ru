---
title: "Макросы рекурсии | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, recursion macros
- recursion macros
- macros, recursion
ms.assetid: c53e5ae7-619e-46b1-bdc2-86d8c7798b1d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e8d9ef7f194151fb3259712759d0c29ed157d564
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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