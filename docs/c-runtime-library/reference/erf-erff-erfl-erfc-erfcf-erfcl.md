---
title: "erf, erff, erfl, erfc, erfcf, erfcl | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- erff
- erfl
- erf
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
- erfl
- erf
- erff
dev_langs:
- C++
helpviewer_keywords:
- erfl function
- erff function
- erf function
ms.assetid: 144d90d3-e437-41c2-a659-cd57596023b5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fa60c6bb6c3c11a596589a411a7d094cc41c65fa
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="erf-erff-erfl-erfc-erfcf-erfcl"></a>erf, erff, erfl, erfc, erfcf, erfcl
Вычисляет функцию ошибок или дополнительную функцию ошибок значения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
double erf(  
   double x  
);  
float erf(  
   float x  
); // C++ only  
long double erf(  
   long double x  
); // C++ only  
float erff(  
   float x  
);  
long double erfl(  
   long double x  
);  
double erfc(  
   double x  
);  
float erfc(  
   float x  
); // C++ only  
long double erfc(  
   long double x  
); // C++ only  
float erfcf(  
   float x  
);  
long double erfcl(  
   long double x  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `x`  
 Значение с плавающей запятой.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функция `erf` возвращает функцию Гаусса (нормального распределения) ошибок `x`. Функция `erfc` возвращает дополнительную функцию Гаусса (нормального распределения) ошибок `x`.  
  
## <a name="remarks"></a>Примечания  
 Функция `erf` вычисляет функцию Гаусса ошибок значения x, которая определяется как:  
  
 ![Функция ошибок от x](../../c-runtime-library/reference/media/crt_erf_formula.PNG "CRT_erf_formula")  
  
 Функция Гаусса ошибок определяется как 1 - erf(x). Функция `erf` возвращает значение в диапазоне от -1,0 до 1,0. Ошибка не возвращается. Функция `erfc` возвращает значение в диапазоне от 0 до 2. Если значение `x` слишком большое для `erfc`, переменная `errno` задается равной `ERANGE`.  
  
 Поскольку C++ допускает перегрузку, можно вызывать перегрузки `erf` и `erfc`, которые принимают и возвращают типы `float` и `long double`. В программе на языке C `erf` и `erfc` всегда принимают и возвращают значение `double`.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`erf`, `erff`, `erfl`, `erfc`, `erfcf`, `erfcl`|\<math.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)