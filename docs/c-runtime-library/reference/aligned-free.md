---
title: "_aligned_free | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _aligned_free
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- aligned_free
- _aligned_free
dev_langs:
- C++
helpviewer_keywords:
- _aligned_free function
- aligned_free function
ms.assetid: ed1ce952-cdfc-4682-85cc-f75d4101603d
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.openlocfilehash: 8cd24f11b79ef4148c1a56521ef85593cf766e2e
ms.lasthandoff: 02/24/2017

---
# <a name="alignedfree"></a>_aligned_free
Освобождает блок памяти, который был выделен с помощью функции [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) или [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void _aligned_free (  
   void *memblock  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `memblock`  
 Указатель на блок памяти, возвращенный в функцию `_aligned_malloc` или `_aligned_offset_malloc`.  
  
## <a name="remarks"></a>Примечания  
 Функция `_aligned_free` помечена как `__declspec(noalias)`; это означает, что функция гарантировано не изменяет глобальные переменные. Дополнительные сведения см. в разделе [noalias](../../cpp/noalias.md).  
  
 Эта функция в отличие от других функций CRT _aligned не проверяет свой параметр. Если `memblock` представляет собой указатель `NULL`, эта функция просто не выполняет никаких действий. Она не влияет на `errno` и не вызывает обработчик недопустимых параметров. Если в функции возникает ошибка, связанная с тем, что предварительно для выделения блоков памяти не использовались функции _aligned либо в результате непредвиденного сбоя возникла ошибка распределения памяти, функция создает отчет отладки, используя [макросы _RPT, _RPTF, _RPTW, _RPTFW](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_aligned_free`|\<malloc.h>|  
  
## <a name="example"></a>Пример  
 Дополнительные сведения см. в разделе [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md).  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>См. также  
 [Выравнивание данных](../../c-runtime-library/data-alignment.md)
