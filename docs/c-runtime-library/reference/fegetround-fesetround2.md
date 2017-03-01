---
title: "fegetround, fesetround2 | Документы Майкрософт"
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
- fegetround
- fesetround
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fegetround
- fesetround
- fenv/fegetround
- fenv/fesetround
dev_langs:
- C++
helpviewer_keywords:
- fegetround function
- fesetround function
ms.assetid: 596af00b-be2f-4f57-b2f5-460485f9ff0b
caps.latest.revision: 6
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: d5dc5278320308f423040d0e07c6cb72af3dd362
ms.lasthandoff: 02/24/2017

---
# <a name="fegetround-fesetround"></a>fegetround, fesetround
Получает или задает текущий режим округления с плавающей запятой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int fegetround(void);  
  
int fesetround(  
   int round_mode  
);   
```  
  
#### <a name="parameters"></a>Параметры  
 `round_mode`  
 Задаваемый режим округления в виде одного из округляющих макросов. Если значение не равно одному из округляющих макросов с плавающей запятой, режим округления не изменяется.  
  
## <a name="return-value"></a>Возвращаемое значение  
 При успешном выполнении `fegetround` возвращает режим округления как одно из значений округляющего макроса с плавающей запятой. Возвращается отрицательное значение, если текущий режим округления невозможно определить.  
  
 При успешном выполнении `fesetround` возвращает 0. В противном случае возвращается ненулевое значение.  
  
## <a name="remarks"></a>Заметки  
 Операции с плавающей запятой могут использовать один из нескольких режимов округления. Они управляют направлением, в котором округляются результаты операций с плавающей запятой при сохранении. Это имена и поведение округляющего макроса с плавающей запятой, заданного в \<fenv.h>:  
  
|Макрос|Описание|  
|-----------|-----------------|  
|FE_DOWNWARD|Округление в сторону отрицательной бесконечности.|  
|FE_TONEAREST|Округление в сторону ближайшего целого числа.|  
|FE_TOWARDZERO|Округление к нулю.|  
|FE_UPWARD|Округление в сторону положительной бесконечности|  
  
 Поведение по умолчанию FE_TONEAREST — округление результатов представляемых значений в сторону ближайшего значения с четным (0), наименее значимым битом.  
  
 Текущий режим округления затрагивает следующие операции.  
  
-   Преобразование строк.  
  
-   Результаты арифметических операций с плавающей запятой за пределами константных выражений.  
  
-   Округляющие функции библиотеки, такие как `rint` и `nearbyint`.  
  
-   Значения, возвращаемые из математических функций стандартной библиотеки.  
  
 Текущий режим округления не затрагивает следующие операции.  
  
-   Функции библиотеки `trunc`, `ceil`, `floor`и `lround` .  
  
-   Приведения и преобразования с плавающей запятой, которые всегда округляются в сторону нуля.  
  
-   Результаты арифметических операторов с плавающей запятой в константных выражениях, которые всегда округляются в сторону ближайшего целого значения.  
  
 Чтобы использовать эти функции, необходимо выключить оптимизации с плавающей запятой, которые могут препятствовать доступу, с помощью директивы `#pragma fenv_access(on)` перед вызовом. Дополнительные сведения см. в разделе [fenv_access](../../preprocessor/fenv-access.md).  
  
## <a name="requirements"></a>Требования  
  
|Функция|Заголовок C|Заголовок C++|  
|--------------|--------------|------------------|  
|`fegetround`,                `fesetround`|\<fenv.h>|\<cfenv>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [nearbyint, nearbyintf, nearbyintl](../../c-runtime-library/reference/nearbyint-nearbyintf-nearbyintl1.md)   
 [rint, rintf, rintl](../../c-runtime-library/reference/rint-rintf-rintl.md)   
 [lrint, lrintf, lrintl, llrint, llrintf, llrintl](../../c-runtime-library/reference/lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)
