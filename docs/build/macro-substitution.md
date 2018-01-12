---
title: "Макроподстановка | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, macro substitution
- macros, NMAKE
- substitution macros in NMAKE
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7c2ea7a2509e58cfd4da163cc76c018d06c244fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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