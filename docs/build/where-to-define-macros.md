---
title: Где следует определять макросы | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9cf3e87a50362c770d45f00c4dc17ac3d264f611
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380918"
---
# <a name="where-to-define-macros"></a>Где следует определять макросы
Макросы определяются в командной строке, командный файл, makefile или файле Tools.ini.  
  
 В файле makefile или файле Tools.ini каждое определение макроса должны располагаться в отдельной строке и не может начинаться с пробела или табуляции. Пробелы или знаки табуляции около знака равенства игнорируются. Все [строка символов](../build/defining-an-nmake-macro.md) являются литералами, в том числе заключающие кавычки и пробелы.  
  
 В командной строке или командный файл пробелов и табуляций разделяя аргументы и не могут стоять рядом знак равенства. Если `string` содержит внедренные пробелы или знаки табуляции, следует заключить саму строку или весь макрос в двойные кавычки (» «).  
  
## <a name="see-also"></a>См. также  
 [Определение макроса NMAKE](../build/defining-an-nmake-macro.md)