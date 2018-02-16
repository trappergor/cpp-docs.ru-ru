---
title: "_flushall | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _flushall
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _flushall
dev_langs:
- C++
helpviewer_keywords:
- flushall function
- flushing streams
- streams, flushing
- _flushall function
ms.assetid: 2cd73562-6d00-4ca2-b13c-80d0ae7870b5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 25e8a0045758d22a9b519cd1ffe4cc675a7674c2
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="flushall"></a>_flushall
Сбрасывает все потоки; очищает все буферы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _flushall( void );  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 `_flushall` возвращает число открытых потоков (ввода и вывода). Ошибка не возвращается.  
  
## <a name="remarks"></a>Примечания  
 По умолчанию функция `_flushall` записывает в соответствующие файлы содержимое всех буферов, связанных с открытыми потоками вывода. Все буферы, связанные с открытыми входными потоками, очищаются. (Эти буферы обычно обслуживаются операционной системой, которая автоматически определяет оптимальное время записи данных на диск: при заполнении буфера, при закрытии потока или при нормальном завершении программы без закрытия потоков).  
  
 Если после вызова функции `_flushall` выполняется операция чтения, из входных файлов в буферы считываются новые данные. После вызова функции `_flushall` все потоки остаются открытыми.  
  
 Предусмотренная в библиотеке времени выполнения функция фиксации на диск позволяет обеспечить запись критически важных данных непосредственно на диск, а не в буферы операционной системы. Эту функцию можно включить, не переписывая программу, а скомпоновав объектные файлы программы с файлом Commode.obj. В создаваемом исполняемом файле вызовы функции `_flushall` записывают содержимое всех буферов на диск. Файл Commode.obj влияет только на функции `_flushall` и `fflush`.  
  
 Дополнительные сведения об управлении возможностью фиксации на диск см. в разделах [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md), [fopen](../../c-runtime-library/reference/fopen-wfopen.md) и [_fdopen](../../c-runtime-library/reference/fdopen-wfdopen.md).  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`_flushall`|\<stdio.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_flushall.c  
// This program uses _flushall  
// to flush all open buffers.  
  
#include <stdio.h>  
  
int main( void )  
{  
   int numflushed;  
  
   numflushed = _flushall();  
   printf( "There were %d streams flushed\n", numflushed );  
}  
```  
  
```Output  
There were 3 streams flushed  
```  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [_commit](../../c-runtime-library/reference/commit.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)