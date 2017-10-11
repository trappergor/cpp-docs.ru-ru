---
title: "lrint, lrintf, lrintl, llrint, llrintf, llrintl | Документы Майкрософт"
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
- lrint
- lrintl
- lrintf
- llrint
- llrintf
- llrintl
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
- lrint
- lrintf
- lrintl
- llrint
- llrintf
- llrintl
- math/lrint
- math/lrintf
- math/lrintl
- math/llrint
- math/llrintf
- math/llrintl
dev_langs:
- C++
helpviewer_keywords:
- lrint function
- lrintf function
- lrintl function
- llrint function
- llrintf function
- llrintl function
ms.assetid: 28ccd5b3-5e6f-434f-997d-a21d51b8ce7f
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 731c3670e315889fdf35e84a234d658b6a904050
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="lrint-lrintf-lrintl-llrint-llrintf-llrintl"></a>lrint, lrintf, lrintl, llrint, llrintf, llrintl
Округляет указанное значение с плавающей запятой до ближайшего целого значения, используя текущие режим и направление округления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
long int lrint(  
   double x  
);  
  
long int lrint(  
   float x  
); //C++ only  
  
long int lrint(  
   long double x  
); //C++ only  
  
long int lrintf(  
   float x  
);  
  
long int lrintl(  
   long double x  
);  
  
long long int llrint(  
   double x  
);  
  
long long int llrint(  
   float x  
); //C++ only  
  
long long int llrint(  
   long double x  
); //C++ only  
  
long long int llrintf(  
   float x  
);  
  
long long int llrintl(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `x`  
 Значение для округления.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает округленное целочисленное значение `x`.  
  
|Проблеми|Назад|  
|-----------|------------|  
|`x` находится за пределами диапазона типа возвращаемого значения<br /><br /> `x` = ±∞<br /><br /> `x` = NaN|Вызывает исключение FE_INVALID и возвращает ноль (0).|  
  
## <a name="remarks"></a>Примечания  
 Так как C++ допускает перегрузку, можно вызывать перегрузки функций `lrint` и `llrint`, принимающие типы значений float и long double. В программе на языке C функции `lrint` и `llrint` всегда принимают и возвращают значения типа double.  
  
 Если `x` не представляет эквивалент целочисленного значения с плавающей запятой, эти функции вызывают исключение FE_INEXACT.  
  
 **Только для систем Майкрософт**. Если результат находится вне диапазона типа возвращаемого значения или параметр является значением NaN или бесконечностью, возвращаемое значение определяется реализацией. Компилятор Майкрософт возвращает нулевое значение (0).  
  
## <a name="requirements"></a>Требования  
  
|Функция|Заголовок C|Заголовок C++|  
|--------------|--------------|------------------|  
|`lrint`,                `lrintf`, `lrintl`, `llrint`, `llrintf`, `llrintl`|\<math.h>|\<cmath>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)
