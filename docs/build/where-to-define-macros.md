---
title: "Где следует определять макросы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c2e646de4cf67fc249d69fb07789f4c8a3e14bf0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="where-to-define-macros"></a>Где следует определять макросы
Макросы определяются в командной строке, командный файл, makefile или файле Tools.ini.  
  
 В файле makefile или файле Tools.ini каждое определение макроса должны располагаться в отдельной строке и не может начинаться с пробела или табуляции. Пробелы или знаки табуляции около знака равенства игнорируются. Все [строка символов](../build/defining-an-nmake-macro.md) являются литералами, в том числе заключающие кавычки и пробелы.  
  
 В командной строке или командный файл пробелов и табуляций разделяя аргументы и не могут стоять рядом знак равенства. Если `string` содержит внедренные пробелы или знаки табуляции, следует заключить саму строку или весь макрос в двойные кавычки (» «).  
  
## <a name="see-also"></a>См. также  
 [Определение макроса NMAKE](../build/defining-an-nmake-macro.md)