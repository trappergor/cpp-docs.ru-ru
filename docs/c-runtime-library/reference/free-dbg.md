---
title: "_free_dbg | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _free_dbg
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
- _free_dbg
- free_dbg
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, deallocating
- freeing memory
- _free_dbg function
- free_dbg function
ms.assetid: fc5e8299-616d-48a0-b979-e037117278c6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 575c683ed1726d9bcaf5e4a1eb850f4b589b4492
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2018
---
# <a name="freedbg"></a>_free_dbg
Освобождает блок памяти в куче (только в отладочной версии).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void _free_dbg(   
   void *userData,  
   int blockType   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `userData`  
 Указатель на выделенный блок памяти, который требуется освободить.  
  
 `blockType`  
 Тип выделенного блока памяти, который требуется освободить: `_CLIENT_BLOCK`, `_NORMAL_BLOCK` или `_IGNORE_BLOCK`.  
  
## <a name="remarks"></a>Примечания  
 `_free_dbg` — это отладочная версия функции [free](../../c-runtime-library/reference/free.md). Если [_DEBUG](../../c-runtime-library/debug.md) не определен, каждый вызов функции `_free_dbg` сокращается до вызова функции `free`. И `free`, и `_free_dbg` освобождают блок памяти в основной куче, однако `_free_dbg` включает две возможности отладки: возможность хранить освободившиеся блоки в связанном списке кучи для моделирования условий недостатка памяти, а также параметр типа блока для освобождения блоков выделенной памяти конкретного типа.  
  
 `_free_dbg` выполняет проверку действительности для всех указанных файлов и расположений блоков перед выполнением операции освобождения. Приложение не ожидает предоставления этих сведений. Когда освобождается блок памяти, диспетчер отладочной кучи автоматически проверяет целостность буферов по обеим сторонам пользовательской части и выдает отчет об ошибке в случае их перезаписи. Если задано битовое поле `_CRTDBG_DELAY_FREE_MEM_DF` флага [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md), освободившийся блок заполняется значением 0xDD, ему назначается тип блока `_FREE_BLOCK` и он хранится в связанном списке блоков памяти кучи.  
  
 В случае возникновения ошибки при освобождении памяти для `errno` задаются сведения о характере сбоя, полученные от операционной системы. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Сведения о типах блоков выделения и способах их использования см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details). Сведения о различиях между вызовом стандартной функции кучи и ее отладочной версии в сборке отладки приложения см. в разделе [Версии отладки функций выделения кучи](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_free_dbg`|\<crtdbg.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 Пример использования функции `_free_dbg` см. в разделе [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).  
  
## <a name="see-also"></a>См. также  
 [Подпрограммы отладки](../../c-runtime-library/debug-routines.md)   
 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)