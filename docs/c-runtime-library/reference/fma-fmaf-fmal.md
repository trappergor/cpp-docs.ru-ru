---
title: "fma, fmaf, fmal | Документы Майкрософт"
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
- fma
- fmaf
- fmal
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
f1_keywords:
- fma
- fmaf
- fmal
- math/fma
- math/fmaf
- math/fmal
dev_langs: C++
helpviewer_keywords:
- fma function
- fmaf function
- fmal function
ms.assetid: 584a6037-da1e-4e86-9f0c-97aae86de0c0
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cd4178718380502e91bb7f019164f2398c93323c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fma-fmaf-fmal"></a>fma, fmaf, fmal
Перемножает два значения, добавляет к произведению третье значение и затем округляет результат без потери точности, вызванной промежуточным округлением.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
double fma(  
   double x,   
   double y,   
   double z  
);  
  
float fma(  
   float  x,   
   float  y,   
   float z  
); //C++ only  
  
long double fma(  
   long double  x,   
   long double  y,   
   long double z  
); //C++ only  
  
float fmaf(  
   float  x,   
   float  y,   
   float z  
);  
  
long double fmal(  
   long double  x,   
   long double  y,   
   long double z  
);  
  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `x`  
 Первое значение для перемножения.  
  
 [in] `y`  
 Второе значение для перемножения.  
  
 [in] `z`  
 Значение для сложения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает `(x * y) + z`. Возвращаемое значение округляется с использованием текущего формата округления.  
  
 В случае неудачи может возвращать одно из следующих значений:  
  
|Проблеми|Назад|  
|-----------|------------|  
|`x` = INFINITY, `y` = 0 или<br /><br /> `x` = 0, `y` = INFINITY|NaN|  
|`x` или `y` = точное значение ± INFINITY, `z` = INFINITY с противоположным знаком|NaN|  
|`x` или `y` = NaN|NaN|  
|не (`x` = 0, `y`= неопределенное значение) и `z` = NaN<br /><br /> не (`x`= неопределенное значение, `y`=0) и `z` = NaN|NaN|  
|Ошибка переполнения диапазона|±HUGE_VAL, ±HUGE_VALF или ±HUGE_VALL|  
|Ошибка недостаточного заполнения диапазона|правильное значение (после округления).|  
  
 Ошибки сообщаются, как указано в [_matherr](../../c-runtime-library/reference/matherr.md).  
  
## <a name="remarks"></a>Примечания  
 Поскольку C++ допускает перегрузку, можно вызывать перегрузки `fma` , принимающие и возвращающие **float** и **long double** типов. В программе на языке C `fma` всегда принимает и возвращает **двойные**.  
  
 Эта функция вычисляет значение с бесконечной точностью, после чего округляет результат.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Заголовок C|Заголовок C++|  
|--------------|--------------|------------------|  
|`fma`, `fmaf`, `fmal`|\<math.h>|\<cmath>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [remainder, remainderf, remainderl](../../c-runtime-library/reference/remainder-remainderf-remainderl.md)   
 [remquo, remquof, remquol](../../c-runtime-library/reference/remquo-remquof-remquol.md)