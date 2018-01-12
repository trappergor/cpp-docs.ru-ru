---
title: "nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- nextafterf
- _nextafterf
- nextafter
- nextafterl
- _nextafter
- nexttoward
- nexttowardf
- nexttowardl
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
- nextafter
- _nextafter
- nextafterf
- nextafterl
- _nextafterf
- math/nextafter
- math/nextafterf
- math/nextafterl
- nexttoward
- nexttowardf
- nexttowardl
- math/nexttoward
- math/nexttowardf
- math/nexttowardl
dev_langs: C++
helpviewer_keywords:
- _nextafter function
- nextafter function
- _nextafterf function
- nextafterf function
- nextafterl function
- nexttoward function
- nexttowardf function
- nexttowardl function
ms.assetid: 9785bfb9-de53-4bd0-9637-f05fa0c1f6ab
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 798e39624c617d8178a7598e74451ca2851cfe12
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="nextafter-nextafterf-nextafterl-nextafter-nextafterf-nexttoward-nexttowardf-nexttowardl"></a>nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl
Возвращает следующее представимое значение с плавающей запятой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
double nextafter(  
   double x,  
   double y   
);  
  
float nextafter(  
   float x,  
   float y   
); /* C++ only, requires <cmath> */  
  
long double nextafter(  
   long double x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
float nextafterf(  
   float x,  
   float y   
);   
  
long double nextafterl(  
   long double x,  
   long double y   
);  
  
double _nextafter(  
   double x,  
   double y   
);  
  
float _nextafterf(  
   float x,  
   float y   
); /* x64 only */  
  
double nexttoward(  
   double x,  
   long double y   
);  
  
float nexttoward(  
   float x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
long double nexttoward(  
   long double x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
float nexttowardf(  
   float x,  
   long double y   
);   
  
long double nexttowardl(  
   long double x,  
   long double y   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `x`  
 Начальное значение с плавающей запятой.  
  
 `y`  
 Следующее значение с плавающей запятой.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает следующее представимое значение с плавающей запятой возвращаемого типа, следующее за значением `x` в направлении значения `y`. Если `x` = `y`, функция возвращает значение `y`, преобразованное в возвращаемый тип, при этом исключение не запускается. Если значение `x` не равно значению `y` и результатом является денормализованное число или нуль, то задаются состояния исключения с плавающей запятой FE_UNDERFLOW и FE_INEXACT, и возвращается правильный результат. Если параметр `x` или `y` имеет значение NAN, то возвращаемое значение является одним из входных значений NaN. Если функция `x` является конечной, а результат является бесконечным или не может быть представлен как имеющий тип, то возвращается значение NAN или соответствующая бесконечность со знаком, задаются состояния исключения с плавающей запятой FE_OVERFLOW и FE_INEXACT, а для`errno` задается значение ERANGE.  
  
## <a name="remarks"></a>Примечания  
 Семейства функций `nextafter` и `nexttoward` эквивалентны за исключением типа параметра `y`. Если значения `x` и `y` равны, возвращается значение `y`, преобразованное в возвращаемый тип.  
  
 Так как C++ допускает перегрузку, то при включении \<cmath> можно вызывать перегрузки `nextafter` и `nexttoward`, которые возвращают типы `float` и `long double`. В программе на языке C функции `nextafter` и `nexttoward` всегда возвращают значения типа `double`.  
  
 Функции `_nextafter` и `_nextafterf` относятся только к системам Майкрософт. Функция `_nextafterf` доступна только при компиляции для x64.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок (C)|Обязательный заголовок (C++)|  
|-------------|---------------------------|-------------------------------|  
|`nextafter`, `nextafterf`, `nextafterl`, `_nextafterf`, `nexttoward`, `nexttowardf`, `nexttowardl`|\<math.h>|\<math.h> или \<cmath>|  
|`_nextafter`|\<float.h>|\<float.h> или \<cfloat>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="see-also"></a>См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [isnan, _isnan, _isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)