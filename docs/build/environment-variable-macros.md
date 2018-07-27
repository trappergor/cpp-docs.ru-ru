---
title: Макросы переменных среды | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, environment variable macros
- environment variables, macros in NMAKE
- macros, environment-variable
ms.assetid: f8e96635-0906-47b0-9f56-12a6fdf5e347
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ebebb6e7d237746f96c7ac7e27c249244ff825b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367437"
---
# <a name="environment-variable-macros"></a>Макросы переменных среды
NMAKE наследует определения макроса для переменных среды, существующих до начала сеанса. Если переменная была задана в среде операционной системы, доступной в качестве макроса NMAKE. Унаследованные имена преобразуются в верхний регистр. Наследование происходит до предварительной обработки. Параметр /E макросы, унаследованные от переменных среды, чтобы переопределить любые макросы с тем же именем в файле makefile.  
  
 Макросы переменных среды может быть переопределен в сеансе, и при этом изменяется соответствующей переменной среды. Можно также изменить переменные среды с помощью команды SET. С помощью команды SET для изменения переменной среды в сеансе не соответствующего макроса, однако изменить.  
  
 Пример:  
  
```  
PATH=$(PATH);\nonesuch  
  
all:  
    echo %PATH%  
```  
  
 В этом примере изменение `PATH` изменяет соответствующей переменной среды `PATH`; она добавляет `\nonesuch` в нужный путь.  
  
 Если переменная среды определяется как строка, которая является синтаксически неправильной в файле makefile, макрос не создается и предупреждение не создается. Если значение переменной содержит знак доллара ($), NMAKE обрабатывает его как начало вызова макроса. Использование макроса может привести к непредвиденному поведению.  
  
## <a name="see-also"></a>См. также  
 [Специальные макросы NMAKE](../build/special-nmake-macros.md)