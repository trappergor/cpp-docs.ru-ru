---
title: "fmin, fminf, fminl | Документы Microsoft"
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
- fmin
- fminf
- fminl
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
- fmin
- fminf
- fminl
- math/fmin
- math/fminf
- math/fminl
helpviewer_keywords:
- fmin function
- fminf function
- fminl function
ms.assetid: 1916dfb5-99c1-4b0d-aefb-513525c3f2ac
caps.latest.revision: 5
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
translationtype: Machine Translation
ms.sourcegitcommit: 8953e3bd81158ce183e1abb5dfa969164c1f9ced
ms.openlocfilehash: b7fd6a2b91c1bc7cd973d2ac60f2d6fc39d322bb
ms.lasthandoff: 02/24/2017

---
# <a name="fmin-fminf-fminl"></a>fmin, fminf, fminl
Определяет наименьшее из двух указанных значений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
double fmin(  
   double x,   
   double y  
);  
  
float fmin(  
   float x,   
   float y  
); //C++ only  
  
long double fmin(  
   long double x,   
   long double y  
); //C++ only  
  
float fminf(  
   float x,   
   float y  
);  
  
long double fminl(  
   long double x,   
   long double y  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `x`  
 Первое сравниваемое значение.  
  
 `y`  
 Второе сравниваемое значение.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает меньшее из значений `x` или `y`.  
  
|Ввод|Результат|  
|-----------|------------|  
|`x` имеет значение NaN|`y`|  
|`y` имеет значение NaN|`x`|  
|`x` и `y` имеют значения NaN|NaN|  
  
 Эта функция не вызывает [_matherr](../../c-runtime-library/reference/matherr.md), исключения вычислений с плавающей запятой и не изменяет значение `errno`.  
  
## <a name="remarks"></a>Примечания  
 Так как C++ допускает перегрузку, можно вызывать перегрузки функции `fmin`, принимающие и возвращающие типы значений с плавающей запятой и длинных двойных значений. В программе на языке C `fmin` всегда принимает и возвращает двойное значение.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`fmin`, `fminf`, `fminl`|C: \<math.h><br />C++: \<math.h> или \<cmath>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)  
 [fmax, fmaxf, fmaxl](fmax-fmaxf-fmaxl.md)  
