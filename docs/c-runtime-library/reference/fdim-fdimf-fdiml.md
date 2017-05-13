---
title: "fdim, fdimf, fdiml | Документы Майкрософт"
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
- fdim
- fdimf
- fdiml
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
- fdim
- fdimf
- fdiml
- math/fdim
- math/fdimf
- math/fdiml
dev_langs:
- C++
helpviewer_keywords:
- fdim function
- fdimf function
- fdiml function
ms.assetid: 2d4ac639-51e9-462d-84ab-fb03b06971a0
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: f13291a00b97c319ebe69bce6939a95e6c022fd8
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="fdim-fdimf-fdiml"></a>fdim, fdimf, fdiml
Определяет положительную разность между первым и вторым значениями.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
double fdim(  
   double x,   
   double y  
);  
  
float fdim(  
   float x,   
   float y  
); //C++ only  
  
long double fdim(  
   long double x,   
   long double y  
); //C++ only  
  
float fdimf(  
   float x,   
   float y  
);  
  
long double fdiml(  
   long double x,   
   long double y  
);  
  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `x`  
 Первое значение в вычитании.  
  
 [in] `y`  
 Второе значение в вычитании.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает положительную разность между `x` и `y`:  
  
|Возвращаемое значение|Сценарий|  
|------------------|--------------|  
|x-y|если x > y|  
|0|если x <= y|  
  
 В случае неудачи может возвращать одну из следующих ошибок:  
  
|Проблеми|Назад|  
|-----------|------------|  
|Ошибка переполнения диапазона|+HUGE_VAL, +HUGE_VALF или +HUGE_VALL|  
|Ошибка недостаточного заполнения диапазона|правильное значение (после округления)|  
|`x` или `y` имеет значение NaN|NaN|  
  
 Ошибки сообщаются, как указано в [_matherr](../../c-runtime-library/reference/matherr.md).  
  
## <a name="remarks"></a>Примечания  
 Так как C++ допускает перегрузку, можно вызывать перегрузки функции `fdim`, принимающие и возвращающие типы значений с плавающей запятой и длинных двойных значений. В программе на языке C `fdim` всегда принимает и возвращает двойное значение.  
  
 За исключением обработки NaN, эта функция эквивалентно `fmax(x - y, 0)`.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Заголовок C|Заголовок C++|  
|--------------|--------------|------------------|  
|`fdim`, `fdimf`, `fdiml`|\<math.h>|\<cmath>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fmax, fmaxf, fmaxl](../../c-runtime-library/reference/fmax-fmaxf-fmaxl.md)   
 [abs, labs, llabs, _abs64](../../c-runtime-library/reference/abs-labs-llabs-abs64.md)
