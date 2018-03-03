---
title: "Макросы переменных среды | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, environment variable macros
- environment variables, macros in NMAKE
- macros, environment-variable
ms.assetid: f8e96635-0906-47b0-9f56-12a6fdf5e347
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 69fae15b7a12d990d2fb2c8e457bfdc0407f7702
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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