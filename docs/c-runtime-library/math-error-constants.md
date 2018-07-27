---
title: Константы математических ошибок | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _PLOSS
- _UNDERFLOW
- _TLOSS
- _SING
- _DOMAIN
- _OVERFLOW
dev_langs:
- C++
helpviewer_keywords:
- _TLOSS constant
- _SING constant
- PLOSS constant
- UNDERFLOW constant
- _UNDERFLOW constant
- _OVERFLOW constant
- DOMAIN constant
- OVERFLOW constant
- TLOSS constant
- SING constant
- _DOMAIN constant
- _PLOSS constant
- math error constants
ms.assetid: 4be933a6-674e-45a5-8ac9-090023542f5b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1bb491e8073acf2af525814b595ce79365df0fa1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389043"
---
# <a name="math-error-constants"></a>Константы математических ошибок
## <a name="syntax"></a>Синтаксис  
  
```  
  
#include <math.h>  
  
```  
  
## <a name="remarks"></a>Примечания  
 Математические подпрограммы библиотеки времени выполнения могут генерировать константы математических ошибок.  
  
 Эти ошибки, описанные ниже, соответствуют типам исключений, определенным в файле MATH.H, и возвращаются функцией `_matherr`, когда возникает математическая ошибка.  
  
|Константа|Значение|  
|--------------|-------------|  
|`_DOMAIN`|Значение аргумента функции находится вне домена функции.|  
|`_OVERFLOW`|Результат слишком велик для представления в виде типа возвращаемого значения функции.|  
|`_PLOSS`|Произошла частичная потеря значимости.|  
|`_SING`|Сингулярность аргумента: аргумент функции имеет недопустимое значение. (Например, значение 0 передается в функцию, для которой требуется ненулевое значение.)|  
|`_TLOSS`|Произошла полная потеря значимости.|  
|`_UNDERFLOW`|Результат слишком мал для представления.|  
  
## <a name="see-also"></a>См. также  
 [_matherr](../c-runtime-library/reference/matherr.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)