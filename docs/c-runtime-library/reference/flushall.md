---
title: _flushall
ms.date: 4/2/2020
api_name:
- _flushall
- _o__flushall
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 93181c0fe941a1c5e259e706771495666329bcb3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346623"
---
# <a name="_flushall"></a>_flushall

Сбрасывает все потоки; очищает все буферы.

## <a name="syntax"></a>Синтаксис

```C
int _flushall( void );
```

## <a name="return-value"></a>Возвращаемое значение

**_flushall** возвращает количество открытых потоков (вход и выход). Ошибка не возвращается.

## <a name="remarks"></a>Remarks

По умолчанию **функция _flushall** записывает в соответствующие файлы содержимое всех буферов, связанных с открытыми потоками вывода. Все буферы, связанные с открытыми входными потоками, очищаются. (Эти буферы обычно обслуживаются операционной системой, которая автоматически определяет оптимальное время записи данных на диск: при заполнении буфера, при закрытии потока или при нормальном завершении программы без закрытия потоков).

Если чтение следует за вызовом **к _flushall,** новые данные считываются из входных файлов в буферы. Все потоки остаются открытыми после звонка **в _flushall.**

Предусмотренная в библиотеке времени выполнения функция фиксации на диск позволяет обеспечить запись критически важных данных непосредственно на диск, а не в буферы операционной системы. Без переписывания существующей программы можно включить эту функцию, связав файлы объектов программы с Commode.obj. В полученном исполняемом файле, призывы **к _flushall** записи содержимого всех буферов на диск. Только **_flushall** и [fflush](fflush.md) страдают от Commode.obj.

Дополнительные сведения об управлении возможностью фиксации на диск см. в разделах [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md), [fopen](fopen-wfopen.md) и [_fdopen](fdopen-wfdopen.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**_flushall**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[_commit](commit.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[setvbuf](setvbuf.md)<br/>
