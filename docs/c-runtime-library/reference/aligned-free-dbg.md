---
title: "_aligned_free_dbg | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _aligned_free_dbg
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
apitype: DLLExport
f1_keywords:
- _aligned_free_dbg
- aligned_free_dbg
dev_langs:
- C++
helpviewer_keywords:
- _aligned_free_dbg function
- aligned_free_dbg function
ms.assetid: eb0cb3c8-0992-4db8-bac3-65f1b8311ca6
caps.latest.revision: 8
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 3522cd33098484194fec8158b26577b9e01dfe62
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="alignedfreedbg"></a>_aligned_free_dbg
Освобождает блок памяти, который был выделен с помощью [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) или [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) (только отладочная версия).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void _aligned_free_dbg(  
   void *memblock  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `memblock`  
 Указатель на блок памяти, возвращенный в функцию `_aligned_malloc` или `_aligned_offset_malloc`.  
  
## <a name="remarks"></a>Примечания  
 Функция `_aligned_free_dbg` — это отладочная версия функции [_aligned_free](../../c-runtime-library/reference/aligned-free.md). Если [_DEBUG](../../c-runtime-library/debug.md) не определен, каждый вызов функции `_aligned_free_dbg` сокращается до вызова функции `_aligned_free`. Оба `_aligned_free` и `_aligned_free_dbg` освобождения блока памяти в основной куче, но `_aligned_free_dbg` включает возможность отладки: возможность хранить освободившиеся блоки в связанном списке кучи для моделирования условий недостатка памяти.  
  
 `_aligned_free_dbg` выполняет проверку действительности для всех указанных файлов и расположений блоков перед выполнением операции освобождения. Приложение не ожидает предоставления этих сведений. Когда освобождается блок памяти, диспетчер отладочной кучи автоматически проверяет целостность буферов по обеим сторонам пользовательской части и выдает отчет об ошибке в случае их перезаписи. Если задано битовое поле `_CRTDBG_DELAY_FREE_MEM_DF` флага [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md), освободившийся блок заполняется значением 0xDD, ему назначается тип блока `_FREE_BLOCK` и он хранится в связанном списке блоков памяти кучи.  
  
 В случае возникновения ошибки при освобождении памяти для `errno` задаются сведения о характере сбоя, полученные от операционной системы. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи см. в разделе [Сведения о куче отладки CRT](/visualstudio/debugger/crt-debug-heap-details). Сведения о типах блоков выделения и способах их использования см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details). Сведения о различиях между вызовом стандартной функции кучи и ее отладочной версии в сборке отладки приложения см. в разделе [Версии отладки функций выделения кучи](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_aligned_free_dbg`|\<crtdbg.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="see-also"></a>См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)
