---
title: "HUGE_VAL _HUGE | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _HUGE
apilocation:
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- _HUGE
- HUGE_VAL
dev_langs:
- C++
helpviewer_keywords:
- _HUGE constant
- HUGE_VAL constant
- double value
ms.assetid: 3f044b45-02cd-46b2-b1de-87fd0441dd6a
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 4c70ea331902ac16e99fcfa214af512f780829d8
ms.lasthandoff: 04/01/2017

---
# <a name="hugeval-huge"></a>HUGE_VAL, _HUGE
## <a name="syntax"></a>Синтаксис  
  
```  
  
#include <math.h>  
  
```  
  
## <a name="remarks"></a>Примечания  
 `HUGE_VAL` является максимальным представимым значением double. Это значение возвращается многими математическими функциями времени выполнения при возникновении ошибки. Для некоторых функций возвращается значение –`HUGE_VAL`. `HUGE_VAL` определяется как `_HUGE`, но математические функции времени выполнения возвращают `HUGE_VAL`. Для согласованности в коде также необходимо использовать значение `HUGE_VAL`.  
  
## <a name="see-also"></a>См. также  
 [Глобальные константы](../c-runtime-library/global-constants.md)
