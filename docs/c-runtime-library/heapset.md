---
title: _heapset | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _heapset
apilocation:
- msvcr90.dll
- msvcr80.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr120.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- _heapset
- heapset
dev_langs:
- C++
helpviewer_keywords:
- checking heap
- heapset function
- heaps, checking
- debugging [CRT], heap-related problems
- _heapset function
ms.assetid: 9667eeb0-55bc-4c19-af5f-d1fd0a142b3c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c45c4cc3e6e6ffe23378ce0b4f26383369e92058
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="heapset"></a>_heapset
Проверяет кучи на предмет минимальной согласованности и задает для свободных записей указанное значение.  
  
> [!IMPORTANT]
>  Эта функция устарела. Начиная с Visual Studio 2015 она недоступна в CRT.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _heapset(   
   unsigned int fill   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `fill`  
 Заполняющий символ.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функция `_heapset` возвращает одну из следующих целочисленных констант манифеста, определенных в файле Malloc.h.  
  
 `_HEAPBADBEGIN`  
 Начальные сведения о заголовке недопустимы или не найдены.  
  
 `_HEAPBADNODE`  
 Куча повреждена или обнаружен плохой узел.  
  
 `_HEAPEMPTY`  
 Куча еще не инициализирована.  
  
 `_HEAPOK`  
 Вероятно, куча согласована.  
  
 Кроме того, при возникновении ошибки функция `_heapset` устанавливает для параметра `errno` значение `ENOSYS`.  
  
## <a name="remarks"></a>Примечания  
 Функция `_heapset` показывает расположения свободной памяти или узлы, которые были непреднамеренно перезаписаны.  
  
 `_heapset` проверяет кучу на предмет минимальной согласованности, а затем задает значение `fill` для каждого байта свободных записей кучи. Это известное значение показывает, какие адреса памяти кучи содержат свободные узлы, а какие содержат данные, которые были непреднамеренно записаны в освободившуюся память. Если операционная система не поддерживает функцию `_heapset`(например, Windows 98), эта функция возвращает `_HEAPOK` и устанавливает для параметра `errno` значение `ENOSYS`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|-------------|---------------------|---------------------|  
|`_heapset`|\<malloc.h>|\<errno.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_heapset.c  
// This program checks the heap and  
// fills in free entries with the character 'Z'.  
  
#include <malloc.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int heapstatus;  
   char *buffer;  
  
   if( (buffer = malloc( 1 )) == NULL ) // Make sure heap is   
      exit( 0 );                        //    initialized       
   heapstatus = _heapset( 'Z' );        // Fill in free entries   
   switch( heapstatus )  
   {  
   case _HEAPOK:  
      printf( "OK - heap is fine\n" );  
      break;  
   case _HEAPEMPTY:  
      printf( "OK - heap is empty\n" );  
      break;  
   case _HEAPBADBEGIN:  
      printf( "ERROR - bad start of heap\n" );  
      break;  
   case _HEAPBADNODE:  
      printf( "ERROR - bad node in heap\n" );  
      break;  
   }  
   free( buffer );  
}  
```  
  
```Output  
OK - heap is fine  
```  
  
## <a name="see-also"></a>См. также  
 [Выделение памяти](../c-runtime-library/memory-allocation.md)   
 [_heapadd](../c-runtime-library/heapadd.md)   
 [_heapchk](../c-runtime-library/reference/heapchk.md)   
 [_heapmin](../c-runtime-library/reference/heapmin.md)   
 [_heapwalk](../c-runtime-library/reference/heapwalk.md)