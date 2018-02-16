---
title: "_set_SSE2_enable | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _set_SSE2_enable
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
- _set_SSE2_enable
- set_SSE2_enable
dev_langs:
- C++
helpviewer_keywords:
- _set_SSE2_enable function
- Streaming SIMD Extensions 2 instructions
- set_SSE2_enable function
ms.assetid: 55db895d-fc1e-475a-9110-b781a9bb51c5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7a1d96390925a81935f9d6d07c7ff5b8ce61a3bf
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="setsse2enable"></a>_set_SSE2_enable
Включает или отключает использование инструкций Streaming SIMD Extensions 2 (SSE2) в математических подпрограммах CRT. (Эта функция недоступна для архитектур x64, поскольку набор инструкций SSE2 включен по умолчанию.)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _set_SSE2_enable(  
   int flag  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `flag`  
 1 для включения реализации SSE2; 0 для отключения реализации SSE2. По умолчанию реализация SSE2 включена для процессоров, которые ее поддерживают.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если реализация SSE2 включена; ноль, если реализация SSE2 отключена.  
  
## <a name="remarks"></a>Примечания  
 Следующие функции имеют реализации SSE2, которые могут быть включены с помощью функции `_set_SSE2_enable`:  
  
-   [atan](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)  
  
-   [ceil](../../c-runtime-library/reference/ceil-ceilf-ceill.md)  
  
-   [exp](../../c-runtime-library/reference/exp-expf.md)  
  
-   [floor](../../c-runtime-library/reference/floor-floorf-floorl.md)  
  
-   [log](../../c-runtime-library/reference/log-logf-log10-log10f.md)  
  
-   [log10](../../c-runtime-library/reference/log-logf-log10-log10f.md)  
  
-   [modf](../../c-runtime-library/reference/modf-modff-modfl.md)  
  
-   [pow](../../c-runtime-library/reference/pow-powf-powl.md)  
  
 SSE2-реализации этих функций могут предоставлять результаты, немного отличающиеся от результатов реализаций по умолчанию, поскольку промежуточными значениями SSE2 являются 64-разрядные числа с плавающей запятой, а промежуточные значения реализаций по умолчанию — 80-разрядные числа с плавающей запятой.  
  
> [!NOTE]
>  Если при компиляции проекта используется параметр компилятора [/Oi (создание встроенных функций)](../../build/reference/oi-generate-intrinsic-functions.md), может оказаться, что функция `_set_SSE2_enable` не оказывает никакого влияния. Параметр компилятора `/Oi` предоставляет компилятору полномочия на использование встроенных функций для замены вызовов CRT; это поведение переопределяет эффект функции `_set_SSE2_enable`. Если необходимо гарантировать, что параметр `/Oi` не переопределяет функцию `_set_SSE2_enable`, используйте при компиляции проекта параметр `/Oi-`. Это также может быть хорошей методикой при использовании других параметров компилятора, подразумевающих `/Oi`.  
  
 Реализация SSE2 используется только в том случае, если все исключения маскированы. Используйте [_control87, _controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md) для маскирования исключений.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_set_SSE2_enable`|\<math.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_set_SSE2_enable.c  
// processor: x86  
#include <math.h>  
#include <stdio.h>  
  
int main()  
{  
   int i = _set_SSE2_enable(1);  
  
   if (i)  
      printf("SSE2 enabled.\n");  
   else  
      printf("SSE2 not enabled; processor does not support SSE2.\n");  
}  
```  
  
 **Вывод**  
  
 `SSE2 enabled.`  
  
## <a name="see-also"></a>См. также  
 [Функции библиотеки CRT](../../c-runtime-library/crt-library-features.md)