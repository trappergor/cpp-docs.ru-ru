---
title: "isnan, _isnan, _isnanf | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _isnan
- _isnanf
- isnan
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
- _isnan
- isnan
- math/isnan
- math/_isnan
- math/_isnanf
- _isnanf
dev_langs: C++
helpviewer_keywords:
- NAN (not a number)
- _isnan function
- IEEE floating-point representation
- Not a Number (NANs)
- isnan function
ms.assetid: 391fbc5b-89a4-4fba-997e-68f1131caf82
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 982760deff4c5e2439c8743aa0de736a24faa02a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="isnan-isnan-isnanf"></a>isnan, _isnan, _isnanf
Проверяет, является ли значение с плавающей запятой нечисловым значением (NAN).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int isnan(  
   /* floating-point */ x   
); /* C-only macro */  
  
int _isnan(  
   double x   
);  
  
int _isnanf(  
   float x  
); /* x64 only */  
  
template <class T>  
bool isnan(  
   T x  
) throw(); /* C++ only */  
```  
  
#### <a name="parameters"></a>Параметры  
 *x*  
 Проверяемое значение с плавающей запятой.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В языке C макрос `isnan`, а также функции `_isnan` и `_isnanf` возвращают ненулевое значение, если аргумент `x` является значением NAN. В остальных случаях возвращается значение 0.  
  
 В языке C++ функции шаблона `isnan` возвращают `true`, если аргумент `x` является значением NAN. В остальных случаях возвращается значение `false`.  
  
## <a name="remarks"></a>Примечания  
 В языке C макрос `isnan`, а также функции `_isnan` и `_isnanf` проверяют значение с плавающей запятой *x* и возвращают ненулевое значение в том случае, если *x* является нечисловым значением (NAN). Значение NAN получается в том случае, если результат операции с плавающей запятой не удается представить в формате IEEE-754 с плавающей запятой для указанного типа. Сведения о том, как значение NaN представляется для вывода, см. в разделе [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
 При компиляции в формате C++ макрос `isnan` не определяется, а вместо него используются функции шаблона `isnan`. Вместо целого возвращается значение типа `bool`.  
  
 Функции `_isnan` и `_isnanf` относятся только к системам Майкрософт. Функция `_isnanf` доступна только при компиляции для x64.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок (C)|Обязательный заголовок (C++)|  
|-------------|---------------------------|-------------------------------|  
|`isnan`, `_isnanf`|\<math.h>|\<math.h> или \<cmath>|  
|`_isnan`|\<float.h>|\<float.h> или \<cfloat>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [_finite, _finitef](../../c-runtime-library/reference/finite-finitef.md)   
 [_fpclass, _fpclassf](../../c-runtime-library/reference/fpclass-fpclassf.md)