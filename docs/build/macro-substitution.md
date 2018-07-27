---
title: Макроподстановка | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, macro substitution
- macros, NMAKE
- substitution macros in NMAKE
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4028ee710cf38b6a4ef929de9a7e4ffad95f3e41
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368074"
---
# <a name="macro-substitution"></a>Макроподстановка
Когда *имя макроса* вызывается, каждое вхождение *string1* в своем определении строки заменяется *string2*.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
$(macroname:string1=string2)  
```  
  
## <a name="remarks"></a>Примечания  
 Макроподстановка чувствительно к регистру и буквально; *string1* и *string2* нельзя вызывать макросы. Подстановка не изменяет исходное определение. Можно заменить текст в любой предопределенный макрос, кроме [ $$@ ](../build/filename-macros.md).  
  
 Не пробелы или знаки табуляции перед двоеточием; любой после двоеточия, интерпретируется как литерал. Если *string2* равен null, все вхождения *string1* удаляются из строки определения макроса.  
  
## <a name="see-also"></a>См. также  
 [Использование макроса NMAKE](../build/using-an-nmake-macro.md)