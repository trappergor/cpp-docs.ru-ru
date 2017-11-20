---
title: "log2, log2f, log2l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- log2
- log2l
- log2f
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
dev_langs: C++
ms.assetid: 94d11b38-70b7-4d3a-94ac-523153c92b2e
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f825304439e3e1c27f5dc1e41a1ae4c311450625
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="log2-log2f-log2l"></a>log2, log2f, log2l
Определяет двоичный логарифм (по основанию 2) для указанного значения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
double log2(  
   double x  
);  
  
float log2(  
   float x  
); //C++ only  
  
long double log2(  
   long double x  
); //C++ only  
  
float log2f(  
   float x  
);  
  
long double log2l(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `x`  
 Значение, для которого вычисляется логарифм по основанию 2.  
  
## <a name="return-value"></a>Возвращаемое значение  
 При успешном выполнении функция возвращает log2 `x`.  
  
 В случае неудачи может возвращать одно из следующих значений:  
  
|Проблеми|Назад|  
|-----------|------------|  
|`x` < 0|NaN|  
|`x` = ±0|-INFINITY|  
|`x` = 1|+0|  
|+INFINITY|+INFINITY|  
|NaN|NaN|  
|ошибка домена|NaN|  
|Ошибка полюса|-HUGE_VAL, -HUGE_VALF или -HUGE_VALL|  
  
 Сообщает об ошибках, как указано в [_matherr](../../c-runtime-library/reference/matherr.md).  
  
## <a name="remarks"></a>Примечания  
 Если x является целым, эта функция фактически возвращает отсчитываемый от нуля индекс 1 самого старшего разряда `x`.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Заголовок C|Заголовок C++|  
|--------------|--------------|------------------|  
|`log2`,                `log2f`, `log2l`|\<math.h>|\<cmath>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [exp2, exp2f, exp2l](../../c-runtime-library/reference/exp2-exp2f-exp2l.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)