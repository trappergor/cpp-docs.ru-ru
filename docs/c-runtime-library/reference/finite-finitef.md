---
title: "_finite, _finitef | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _finite
- _finitef
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
- finite
- _finite
- _finitef
- math/_finite
- math/_finitef
- float/_finite
dev_langs:
- C++
helpviewer_keywords:
- finite function
- _finite function
- _finitef function
ms.assetid: 5a7d7ca7-befb-4e1f-831d-28713c6eb805
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eb904e04e8a99bff242d520f6c0ca3d404a74e89
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="finite-finitef"></a>_finite, _finitef
Определяет, является ли значение с плавающей запятой конечным.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _finite(   
   double x   
);  
  
int _finitef(   
   float x   
); /* x64 and ARM/ARM64 only */  
```  
  
#### <a name="parameters"></a>Параметры  
 `x`  
 Проверяемое значение с плавающей запятой.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Оба `_finite` и `_finitef` возвращает ненулевое значение, если аргумент *x* является конечным, то есть, если -INF < `x` < + INF. Возвращает 0, если аргумент является бесконечным или NAN.  
  
## <a name="remarks"></a>Примечания  
 Функции `_finite` и `_finitef` относятся только к системам Майкрософт. Функция `_finitef` доступна только в случае компиляции для платформ x86, ARM или ARM64.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок (C)|Обязательный заголовок (C++)|  
|--------------|---------------------------|-------------------------------|  
|`_finite`|\<float.h> или \<math.h>|\<float.h>, \<math.h>, \<cfloat> или \<cmath>|  
|`_finitef`|\<math.h>|\<math.h> или \<cmath>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [isnan, _isnan, _isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)   
 [_fpclass, _fpclassf](../../c-runtime-library/reference/fpclass-fpclassf.md)