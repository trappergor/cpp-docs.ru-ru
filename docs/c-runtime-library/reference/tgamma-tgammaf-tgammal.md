---
title: "tgamma, tgammaf, tgammal | Документы Майкрософт"
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
- tgamma
- tgammaf
- tgammal
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
- tgamma
- tgammaf
- tgammal
- math/tgamma
- math/tgammaf
- math/tgammal
dev_langs: C++
helpviewer_keywords:
- tgamma function
- tgammaf function
- tgammal function
ms.assetid: f1bd2681-8af2-48a9-919d-5358fd068acd
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fefaaaf6dd6e660c4cda53d28194d6052d1d8bf4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="tgamma-tgammaf-tgammal"></a>tgamma, tgammaf, tgammal
Определяет гамма-функцию указанного значения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
double tgamma(  
   double x  
);  
  
float tgamma(  
   float x  
); //C++ only  
  
long double tgamma(  
   long double x  
); //C++ only  
  
float tgammaf(  
   float x  
);  
  
long double tgammal(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `x`  
 Значение, для которого требуется найти гамму.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает гамму `x`.  
  
 Ошибка диапазона может возникнуть, если величина `x` слишком большая или слишком маленькая для типа данных. Ошибка домена или диапазона может возникать, если `x` <= 0.  
  
|Проблеми|Назад|  
|-----------|------------|  
|x = ±0|±INFINITY|  
|x = negative integer|NaN|  
|x = –INFINITY|NaN|  
|x = +INFINITY|+INFINITY|  
|x = NaN|NaN|  
|ошибка домена|NaN|  
|ошибка полюса|±HUGE_VAL, ±HUGE_VALF или ±HUGE_VALL|  
|ошибка переполнения диапазона|±HUGE_VAL, ±HUGE_VALF или ±HUGE_VALL|  
|ошибка недостаточного заполнения диапазона|правильное значение (после округления).|  
  
 Ошибки сообщаются, как указано в [_matherr](../../c-runtime-library/reference/matherr.md).  
  
## <a name="remarks"></a>Примечания  
 Так как C++ допускает перегрузку, можно вызывать перегрузки гамма-функции, принимающие и возвращающие типы значений с плавающей запятой и длинных двойных значений. В программе на языке C гамма-функция всегда принимает и возвращает двойное значение.  
  
 Если x является натуральным числом, эта функция возвращает факториал (x – 1).  
  
## <a name="requirements"></a>Требования  
  
|Функция|Заголовок C|Заголовок C++|  
|--------------|--------------|------------------|  
|`tgamma`,                `tgammaf`, `tgammal`|\<math.h>|\<cmath>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [lgamma, lgammaf, lgammal](../../c-runtime-library/reference/lgamma-lgammaf-lgammal.md)