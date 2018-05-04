---
title: Пустой и неопределенный макрос | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, undefined macros
- Null macros in NMAKE
- macros, null and undefined
- undefined macros and NMAKE
- NMAKE program, null macros
ms.assetid: 1db4611a-1755-4328-b00f-d35365af8b6c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 494a084ee5ba1da29c132aa632b647b37f305855
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="null-and-undefined-macros"></a>Пустой и неопределенный макрос
Пустой и неопределенный макросы разворачиваются в пустые строки, но макрос, определенный как строку null, рассматривается как определенный в выражениях предварительной обработки. Чтобы определить макрос как строку null, укажите никакие символы, за исключением пробелов и символов табуляции после знака равенства (=) в командной строке или командный файл и заключите пустую строку или определение в двойные кавычки (» «). Чтобы отменить определение макроса, используйте **! UNDEF.** Дополнительные сведения см. в разделе [директивы предварительной обработки файлов Makefile](../build/makefile-preprocessing-directives.md).  
  
## <a name="see-also"></a>См. также  
 [Определение макроса NMAKE](../build/defining-an-nmake-macro.md)