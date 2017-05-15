---
title: "_fpclass, _fpclassf | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fpclass
- _fpclassf
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
- fpclass
- _fpclass
- _fpclassf
- math/_fpclass
- float/_fpclass
- math/_fpclassf
dev_langs:
- C++
helpviewer_keywords:
- fpclass function
- floating-point numbers, IEEE representation
- _fpclass function
- _fpclassf function
ms.assetid: 2774872d-3543-446f-bc72-db85f8b95a6b
caps.latest.revision: 13
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 9f061841ea6f4050945caeb2cacb9acfdce77c44
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="fpclass-fpclassf"></a>_fpclass, _fpclassf
Возвращает значение, указывающее классификацию числа с плавающей запятой для аргумента.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _fpclass(   
   double x   
);  
  
int _fpclassf(   
   float x   
); /* x64 only */  
```  
  
#### <a name="parameters"></a>Параметры  
 `x`  
 Проверяемое значение с плавающей запятой.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функции `_fpclass` и `_fpclassf` возвращают целое значение, указывающее классификацию числа с плавающей запятой для аргумента `x`. Классификация может иметь одно из следующих значений, определенных в \<float.h>.  
  
|Значение|Описание|  
|-----------|-----------------|  
|`_FPCLASS_SNAN`|Сигнальное значение NaN|  
|`_FPCLASS_QNAN`|Несигнальное значение NaN|  
|`_FPCLASS_NINF`|Отрицательная бесконечность (-INF)|  
|`_FPCLASS_NN`|Отрицательное ненулевое нормализованное значение|  
|`_FPCLASS_ND`|Отрицательное денормализованное значение|  
|`_FPCLASS_NZ`|Отрицательный нуль (- 0)|  
|`_FPCLASS_PZ`|Положительный 0 (+ 0)|  
|`_FPCLASS_PD`|Положительное денормализованное значение|  
|`_FPCLASS_PN`|Положительное ненулевое нормализованное значение|  
|`_FPCLASS_PINF`|Положительная бесконечность (+INF)|  
  
## <a name="remarks"></a>Примечания  
 Функции `_fpclass` и `_fpclassf` относятся только к системам Майкрософт. Они похожи на [fpclassify](../../c-runtime-library/reference/fpclassify.md), но возвращают подробные сведения об аргументе. Функция `_fpclassf` доступна только в случае компиляции для платформы x64.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`_fpclass`|\<float.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [isnan, _isnan, _isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)   
 [fpclassify](../../c-runtime-library/reference/fpclassify.md)
