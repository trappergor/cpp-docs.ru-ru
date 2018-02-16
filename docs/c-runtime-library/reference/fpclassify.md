---
title: "fpclassify | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- fpclassify
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
apitype: HeaderDef
f1_keywords:
- fpclassify
- math/fpclassify
helpviewer_keywords:
- fpclassify macro
- fpclassify function
ms.assetid: bf549499-7ff9-4a58-8692-f2d1cb6bab81
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 81a2c9c5237d455908e1d0e4f58bff87418a7f8b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="fpclassify"></a>fpclassify
Возвращает значение, указывающее классификацию числа с плавающей запятой для аргумента.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int fpclassify(   
   /* floating-point */ x   
);  
  
int fpclassify(   
   float x   
); // C++ only  
  
int fpclassify(   
   double x   
); // C++ only  
  
int fpclassify(   
   long double x   
); // C++ only  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `x`  
 Проверяемое значение с плавающей запятой.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функция `fpclassify` возвращает целое значение, указывающее классификацию числа с плавающей запятой для аргумента `x`. В этой таблице приведены возможные значения, возвращаемые функцией `fpclassify`, определенные в \<math.h>.  
  
|Значение|Описание:|  
|-----------|-----------------|  
|`FP_NAN`|Сигнальное, несигнальное или неопределенное значение NaN|  
|`FP_INFINITE`|Положительная или отрицательная бесконечность|  
|`FP_NORMAL`|Положительное или отрицательное нормализованное ненулевое значение|  
|`FP_SUBNORMAL`|Положительное или отрицательное денормализованное значение|  
|`FP_ZERO`|Положительное или отрицательное нулевое значение|  
  
## <a name="remarks"></a>Примечания  
 В языке C функция `fpclassify` реализована как макрос, а в C++ `fpclassify` — это функция, перегружаемая с использованием аргументов типа `float`, `double` или `long double`. В обоих случаях возвращаемое значение зависит от действительного типа выражения аргумента, а не от промежуточного представления. Например, обычное значение `double` или `long double` при преобразовании в значение `float` может становиться бесконечным, денормализованным или нулевым значением.  
  
## <a name="requirements"></a>Требования  
  
|Функция или макрос|Обязательный заголовок (C)|Обязательный заголовок (C++)|  
|---------------------|---------------------------|-------------------------------|  
|`fpclassify`|\<math.h>|\<math.h> или \<cmath>|  
  
 Макрос `fpclassify` и функции `fpclassify` соответствуют спецификациям C99 и C++11. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [isnan, _isnan, _isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)