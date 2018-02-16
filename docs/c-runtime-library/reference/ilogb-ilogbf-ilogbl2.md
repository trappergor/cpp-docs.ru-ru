---
title: "ilogb, ilogbf, ilogbl2 | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- ilogb
- ilogbf
- ilogbl
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
- ilogb
- ilogbf
- ilogbl
- math/ilogb
- math/ilogbf
- math/ilogbl
helpviewer_keywords:
- ilogb function
- ilogbf function
- ilogbl function
ms.assetid: 9ef19d57-1caa-41d5-8233-2faad3562fcb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8da5ba71b59f64c38a051fd8f31fa7bf58a4556d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="ilogb-ilogbf-ilogbl"></a>ilogb, ilogbf, ilogbl
Возвращает целое число, представляющее несмещенный порядок по основанию 2 для заданного значения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int ilogb(  
   double x  
);  
  
int ilogb(  
   float x  
); //C++ only  
  
int ilogb(  
   long double x  
); //C++ only  
  
int ilogbf(  
   float x  
);  
  
int ilogbl(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `x`  
 Указанное значение.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает порядок по основанию 2 для числа `x` в виде значения типа `int` со знаком.  
  
 В противном случае возвращает одно из следующих значений, определенных в \<math.h>:  
  
|Входные данные|Результат|  
|-----------|------------|  
|±0|FP_ILOGB0|  
|±INF ±nan, не ограничена|FP_ILOGBNAN|  
  
 Сообщает об ошибках, как указано в [_matherr](../../c-runtime-library/reference/matherr.md).  
  
## <a name="remarks"></a>Примечания  
 Так как C++ допускает перегрузку, можно вызывать перегрузки функции `ilogb`, принимающие и возвращающие типы значений с плавающей запятой и длинных двойных значений. В программе на языке C `ilogb` всегда принимает и возвращает значение типа double.  
  
 Вызов этой функции аналогичен вызову эквивалентной функции `logb` с последующим приведением возвращаемого значения к типу `int`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Заголовок C|Заголовок C++|  
|-------------|--------------|------------------|  
|`ilogb`,                `ilogbf`, `ilogbl`|\<math.h>|\<cmath>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [logb, logbf, logbl, _logb, _logbf](../../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)