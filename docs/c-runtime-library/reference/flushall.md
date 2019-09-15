---
title: _flushall
ms.date: 11/04/2016
api_name:
- _flushall
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _flushall
helpviewer_keywords:
- flushall function
- flushing streams
- streams, flushing
- _flushall function
ms.assetid: 2cd73562-6d00-4ca2-b13c-80d0ae7870b5
ms.openlocfilehash: dce7412ccc19d4870494851d366c059ff01de16a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957138"
---
# <a name="_flushall"></a>_flushall

Сбрасывает все потоки; очищает все буферы.

## <a name="syntax"></a>Синтаксис

```C
int _flushall( void );
```

## <a name="return-value"></a>Возвращаемое значение

**_flushall** возвращает количество открытых потоков (входных и выходных). Ошибка не возвращается.

## <a name="remarks"></a>Примечания

По умолчанию функция **_flushall** записывает в соответствующие файлы содержимое всех буферов, связанных с открытыми выходными потоками. Все буферы, связанные с открытыми входными потоками, очищаются. (Эти буферы обычно обслуживаются операционной системой, которая автоматически определяет оптимальное время записи данных на диск: при заполнении буфера, при закрытии потока или при нормальном завершении программы без закрытия потоков).

Если при чтении следует вызов **_flushall**, то новые данные считываются из входных файлов в буферы. После вызова **_flushall**все потоки остаются открытыми.

Предусмотренная в библиотеке времени выполнения функция фиксации на диск позволяет обеспечить запись критически важных данных непосредственно на диск, а не в буферы операционной системы. Эту функцию можно включить, не переписывая программу, а скомпоновав объектные файлы программы с файлом Commode.obj. В результирующем исполняемом файле вызовы **_flushall** записывают содержимое всех буферов на диск. Файлом Commode. obj влияет только на **_flushall** и [fflush](fflush.md) .

Дополнительные сведения об управлении возможностью фиксации на диск см. в разделах [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md), [fopen](fopen-wfopen.md) и [_fdopen](fdopen-wfdopen.md).

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**_flushall**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
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

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[_commit](commit.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[setvbuf](setvbuf.md)<br/>
