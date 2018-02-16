---
title: "expm1, expm1f, expm1l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- expm1l
- expm1
- expm1f
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
- expm1l
- expm1
- expm1f
dev_langs:
- C++
helpviewer_keywords:
- expm1f function
- expm1l function
- expm1 function
ms.assetid: 2a4dd2d9-370c-42b0-9067-0625efa272e0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 85fc89810e37236b4e7e4844931393395f51426d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="expm1-expm1f-expm1l"></a>expm1, expm1f, expm1l
Вычисляет экспоненту значения с основанием e минус один.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
double expm1(   
   double x   
);  
float expm1(  
   float x  
);  // C++ only  
long double expm1(  
   long double x  
);  // C++ only  
float expm1f(  
   float x  
);  
long double expm1l(  
   long double x  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `x`  
 Значение экспоненты с плавающей запятой.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `expm1` Функции возвращают значение с плавающей запятой, представляющий e<sup>x</sup> - 1, в случае успешного выполнения. При переполнении `expm1` возвращает `HUGE_VAL`, `expm1f` возвращает `HUGE_VALF`, `expm1l` возвращает `HUGE_VALL`, а `errno` принимает значение `ERANGE`. Дополнительные сведения о кодах возврата см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Поскольку C++ допускает перегрузку, можно вызывать перегрузки `expm1`, которые принимают и возвращают значения `float` и `long double`. В программе на языке C `expm1` всегда принимает и возвращает `double`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`expm1`, `expm1f`, `expm1l`|\<math.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [exp2, exp2f, exp2l](exp2-exp2f-exp2l.md)   
 [pow, powf, powl](../../c-runtime-library/reference/pow-powf-powl.md)