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
ms.topic: reference
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d90de1e734b2d2da4770c7a5ad85a5ee60a15408
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
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
  
|Входные данные|Результат|  
|-----------|------------|  
|`x` имеет значение NaN|`y`|  
|`y` имеет значение NaN|`x`|  
|`x` и `y` имеют значения NaN|NaN|  
  
 Эта функция не вызывает [_matherr](../../c-runtime-library/reference/matherr.md), исключения вычислений с плавающей запятой и не изменяет значение `errno`.  
  
## <a name="remarks"></a>Примечания  
 Так как C++ допускает перегрузку, можно вызывать перегрузки функции `fmin`, принимающие и возвращающие типы значений с плавающей запятой и длинных двойных значений. В программе на языке C `fmin` всегда принимает и возвращает значение типа double.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`fmin`, `fminf`, `fminl`|C: \<math.h><br />C++: \<math.h> или \<cmath>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)  
 [fmax, fmaxf, fmaxl](fmax-fmaxf-fmaxl.md)  