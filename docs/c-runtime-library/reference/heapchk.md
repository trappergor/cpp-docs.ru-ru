---
title: "_heapchk | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _heapchk
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
- _heapchk
- heapchk
dev_langs: C++
helpviewer_keywords:
- debugging [CRT], heap-related problems
- consistency checking of heaps
- heapchk function
- heaps, checking consistency
- _heapchk function
ms.assetid: 859619a5-1e35-4f02-9e09-11d9fa266ec0
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 790d887009137ccc9115484b2ace57302c94d851
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="heapchk"></a>_heapchk
Выполняет проверки согласованности в куче.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _heapchk( void );  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функция `_heapchk` возвращает одну из следующих целочисленных констант манифеста, определенных в файле Malloc.h.  
  
 `_HEAPBADBEGIN`  
 Начальные сведения о заголовке повреждены или не найдены.  
  
 `_HEAPBADNODE`  
 Обнаружен недопустимый узел или куча повреждена.  
  
 `_HEAPBADPTR`  
 Недопустимый указатель на кучу.  
  
 `_HEAPEMPTY`  
 Куча не инициализирована.  
  
 `_HEAPOK`  
 Вероятно, куча согласована.  
  
 Кроме того, при возникновении ошибки функция `_heapchk` устанавливает для параметра `errno` значение `ENOSYS`.  
  
## <a name="remarks"></a>Примечания  
 Функция `_heapchk` используется при отладке проблем с кучей, обеспечивая проверку минимальной согласованности кучи. Если операционная система не поддерживает функцию `_heapchk`(например, Windows 98), эта функция возвращает `_HEAPOK` и устанавливает для параметра `errno` значение `ENOSYS`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|-------------|---------------------|---------------------|  
|`_heapchk`|\<malloc.h>|\<errno.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_heapchk.c  
// This program checks the heap for  
// consistency and prints an appropriate message.  
  
#include <malloc.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int  heapstatus;  
   char *buffer;  
  
   // Allocate and deallocate some memory  
   if( (buffer = (char *)malloc( 100 )) != NULL )  
      free( buffer );  
  
   // Check heap status  
   heapstatus = _heapchk();  
   switch( heapstatus )  
   {  
   case _HEAPOK:  
      printf(" OK - heap is fine\n" );  
      break;  
   case _HEAPEMPTY:  
      printf(" OK - heap is empty\n" );  
      break;  
   case _HEAPBADBEGIN:  
      printf( "ERROR - bad start of heap\n" );  
      break;  
   case _HEAPBADNODE:  
      printf( "ERROR - bad node in heap\n" );  
      break;  
   }  
}  
```  
  
```Output  
OK - heap is fine  
```  
  
## <a name="see-also"></a>См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [_heapadd](../../c-runtime-library/heapadd.md)   
 [_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [_heapset](../../c-runtime-library/heapset.md)   
 [_heapwalk](../../c-runtime-library/reference/heapwalk.md)