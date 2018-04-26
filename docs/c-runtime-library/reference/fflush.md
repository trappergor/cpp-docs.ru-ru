---
title: fflush | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- fflush
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
- fflush
dev_langs:
- C++
helpviewer_keywords:
- streams, flushing
- flushing
- fflush function
ms.assetid: 8bbc753f-dc74-4e77-b563-74da2835e92b
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a92affa1483c8dba9be0718acc00d4574eb44bb
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="fflush"></a>fflush

Записывает содержимое потока на диск.

## <a name="syntax"></a>Синтаксис

```C
int fflush(
   FILE *stream
);
```

### <a name="parameters"></a>Параметры

*Поток*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

**fflush** возвращает 0, если буфер был успешно сброшен. Кроме того, значение 0 также возвращается в случаях, когда указанный поток не имеет буфера или открыт только для чтения. Возвращаемое значение **EOF** указывает на ошибку.

> [!NOTE]
> Если **fflush** возвращает **EOF**, возможно, была прервана из-за ошибки записи данных. При настройке обработчика критическая ошибка, безопаснее отключить буферизацию с **setvbuf** функции или использовать процедуры низкоуровневого ввода и вывода, такие как **_open**, **_close**, и **_write** вместо функции потока ввода-вывода.

## <a name="remarks"></a>Примечания

**Fflush** функция сохраняет поток *поток*. Если поток был открыт в режиме записи, а также если он был открыт в режиме обновления и последней была выполнена операция записи, содержимое буфера потока записывается в базовый файл или на базовое устройство, после чего буфер очищается. Если поток был открыт в режиме чтения, или в том случае, если поток имеет буфер не вызов **fflush** не влияет, и любой буфер сохраняется. Вызов **fflush** Инвертирует результат любого предыдущего вызова **ungetc** для потока. После вызова поток остается открытым.

Если *поток* — **NULL**, поведение такое же, как вызов **fflush** на каждый открытый поток. Выполняется запись на диск всех потоков, открытых в режиме записи, а также всех потоков в режиме обновления, для которых последней была выполнена операция записи. Вызов не влияет на другие потоки.

Эти буферы обычно обслуживаются операционной системой, которая автоматически определяет оптимальное время записи данных на диск: при заполнении буфера, при закрытии потока или при нормальном завершении программы без закрытия потоков. Предусмотренная в библиотеке времени выполнения возможность фиксации на диск позволяет обеспечить запись критически важных данных непосредственно на диск, а не в буферы операционной системы. Эту возможность можно включить, не переписывая программу, а скомпоновав объектные файлы программы с файлом COMMODE.OBJ. В создаваемом исполняемом файле вызовы **_flushall** записывают содержимое всех буферов на диск. Только **_flushall** и **fflush** затронутые COMMODE.OBJ.

Дополнительные сведения об управлении возможностью фиксации на диск см. в разделах [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md), [fopen](fopen-wfopen.md) и [_fdopen](fdopen-wfdopen.md).

Функция блокирует вызывающий поток, поэтому она потокобезопасна. Неблокирующей версии см. **_fflush_nolock**.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**fflush**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_fflush.c
#include <stdio.h>
#include <conio.h>

int main( void )
{
   int integer;
   char string[81];

   // Read each word as a string.
   printf( "Enter a sentence of four words with scanf: " );
   for( integer = 0; integer < 4; integer++ )
   {
      scanf_s( "%s", string, sizeof(string) );
      printf( "%s\n", string );
   }

   // You must flush the input buffer before using gets.
   // fflush on input stream is an extension to the C standard
   fflush( stdin );
   printf( "Enter the same sentence with gets: " );
   gets_s( string, sizeof(string) );
   printf( "%s\n", string );
}
```

```Output

      This is a test
This is a test

```

```Output

      This is a test
This is a testEnter a sentence of four words with scanf: This is a test
This
is
a
test
Enter the same sentence with gets: This is a test
This is a test
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_flushall](flushall.md)<br/>
[setvbuf](setvbuf.md)<br/>
